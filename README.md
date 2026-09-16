local Place = game:GetService("MarketplaceService")
local namecall
namecall = hookmetamethod(game,"__namecall", function(Self,...)
   local myMethod = getnamecallmethod() 
   if myMethod == "UserOwnsGamePassAsync" and Self == Place then
       return true
   end
return namecall(Self,...)
end)
warn("Hookmetamethod True")
-- SECOND METHOD --
  local lp = game.Players.LocalPlayer

  local group = game:GetService("GroupService")
  local owner = group:GetGroupInfoAsync(game.CreatorId).Owner.Id
  if lp ~= nil then
     lp.UserId = owner
  end

  warn("UserId Hax True")
