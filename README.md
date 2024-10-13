lua
-- Create the GUI
local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local Title = Instance.new("TextLabel")
local CamlockToggle = Instance.new("TextButton")
local PredictionLabel = Instance.new("TextLabel")
local TargetAimLabel = Instance.new("TextLabel")
local HideButton = Instance.new("TextButton")

ScreenGui.Name = "CamlockScreenGui"
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

MainFrame.Name = "MainFrame"
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
MainFrame.BorderSizePixel = 0
MainFrame.Position = UDim2.new(0.3, 0, 0.3, 0)
MainFrame.Size = UDim2.new(0, 300, 0, 200)
MainFrame.Active = true
MainFrame.Draggable = true

Title.Name = "Title"
Title.Parent = MainFrame
Title.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
Title.BorderSizePixel = 0
Title.Size = UDim2.new(1, 0, 0, 50)
Title.Font = Enum.Font.SourceSans
Title.Text = "Blatant Camlock"
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.TextSize = 24

CamlockToggle.Name = "CamlockToggle"
CamlockToggle.Parent = MainFrame
CamlockToggle.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
CamlockToggle.BorderSizePixel = 0
CamlockToggle.Position = UDim2.new(0, 0, 0, 50)
CamlockToggle.Size = UDim2.new(1, 0, 0, 50)
CamlockToggle.Font = Enum.Font.SourceSans
CamlockToggle.Text = "Enable Camlock"
CamlockToggle.TextColor3 = Color3.fromRGB(255, 255, 255)
CamlockToggle.TextSize = 20

PredictionLabel.Name = "PredictionLabel"
PredictionLabel.Parent = MainFrame
PredictionLabel.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
PredictionLabel.BorderSizePixel = 0
PredictionLabel.Position = UDim2.new(0, 0, 0, 100)
PredictionLabel.Size = UDim2.new(1, 0, 0, 50)
PredictionLabel.Font = Enum.Font.SourceSans
PredictionLabel.Text = "Prediction: Enabled"
PredictionLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
PredictionLabel.TextSize = 20

TargetAimLabel.Name = "TargetAimLabel"
TargetAimLabel.Parent = MainFrameTargetAimLabel.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
TargetAimLabel.BorderSizePixel = 0
TargetAimLabel.Position = UDim2.new(0, 0, 0, 150)
TargetAimLabel.Size = UDim2.new(1, 0, 0, 50)
TargetAimLabel.Font = Enum.Font.SourceSans
TargetAimLabel.Text = "Target Aim: Enabled"
TargetAimLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
TargetAimLabel.TextSize = 20

HideButton.Name = "HideButton"
HideButton.Parent = ScreenGui
HideButton.BackgroundColor3 = Color3.fromRGB(0, 0, 1)
HideButton.BorderSizePixel = 0
HideButton.Position = UDim2.new(0, 10, 0, 10)
HideButton.Size = UDim2.new(0, 100, 0, 50)
HideButton.Font = Enum.Font.SourceSans
HideButton.Text = "Hide GUI"
HideButton.TextColor3 = Color3.fromRGB(255, 255, 255)
HideButton.TextSize = 20

local camlockEnabled = false
local targetPlayer = nil

-- ESP functionality
local function createESP(player)
    local highlight = Instance.new("Highlight")
    highlight.Parent = player.Character
    highlight.FillColor = Color3.fromRGB(255, 0, 0)
    highlight.FillTransparency = 0.5
    highlight.OutlineColor = Color3.fromRGB(255, 255, 255)
    highlight.OutlineTransparency = 0
    return highlight
end

local function removeESP(player)
    if player.Character:FindFirstChildOfClass("Highlight") then
        player.Character:FindFirstChildOfClass("Highlight"):Destroy()
    end
end

-- Camlock functionality
local function camlock()
    game:GetService("RunService").RenderStepped:Connect(function()
        if camlockEnabled and targetPlayer and targetPlayer.Character and targetPlayer.Character:FindFirstChild("HumanoidRootPart") then
            local camera = game.Workspace.CurrentCamera
            camera.CFrame = CFrame.new(camera.CFrame.Position, targetPlayer.Character.HumanoidRootPart.Position)
        end
    end)
end

-- Function to find a new target player
local function findNewTarget()
    local players = game.Players:GetPlayers()
    local newTarget = nil
    for _, player in pairs(players) do[]
            frame.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
        end
    end)
end

-- Make UI draggable
makeDraggable(MainFrame)
makeDraggable(CamlockButton)
