local ReplicatedStorage = game:GetService("ReplicatedStorage")
local player = game.Players.LocalPlayer

local Network = require(ReplicatedStorage.Modules.Network)


local itemToBuy = game:GetService("ReplicatedStorage").Assets.Killers["!Herobrine"].Config  

local function buyItem(item)
	
	local e = Network:FireServerConnection(nil,"REMOTE_FUNCTION","PurchaseContent", item)
	pcall(function()
	print(tostring(e))
	end)
end

buyItem()
