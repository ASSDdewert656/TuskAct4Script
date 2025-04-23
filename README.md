local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local hrp = character:WaitForChild("HumanoidRootPart")

local stand = game.ReplicatedStorage:WaitForChild("Tusk3DModel"):Clone()
stand.Parent = workspace
stand:SetPrimaryPartCFrame(hrp.CFrame * CFrame.new(-2, 0, -3))

game:GetService("RunService").RenderStepped:Connect(function()
    if stand and hrp then
        stand:SetPrimaryPartCFrame(hrp.CFrame * CFrame.new(-2, 0, -3))
    end
end)
