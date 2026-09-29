local FishData = require(game.ReplicatedStorage.FishData)

local function getFish()
    local chance = math.random(1,1000)

    if chance == 1000 then
        return FishData.Secret[1]
    elseif chance >= 900 then
        return FishData.Rare[math.random(1,#FishData.Rare)]
    else
        return FishData.Common[math.random(1,#FishData.Common)]
    end
end

game.ReplicatedStorage.FishEvent.OnServerEvent:Connect(function(player)
    local fish = getFish()

    print(player.Name .. " mendapatkan " .. fish.Name)

    local leaderstats = player:FindFirstChild("leaderstats")
    if leaderstats then
        leaderstats.Coins.Value += fish.Value
    end
end)
