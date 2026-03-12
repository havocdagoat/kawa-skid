-- Services
local CoreGui = game:GetService("CoreGui")
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local TweenService = game:GetService("TweenService")
local Lighting = game:GetService("Lighting")
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Workspace = game:GetService("Workspace")
local UserInputService = game:GetService("UserInputService")

-- Color Constants
local MAIN_COLOR = Color3.fromRGB(30, 5, 5)
local STROKE_COLOR = Color3.fromRGB(255, 0, 0)
local TEXT_COLOR = Color3.fromRGB(255, 50, 50)
local SUBTEXT_COLOR = Color3.fromRGB(255, 100, 100)
local ACCENT_COLOR = Color3.fromRGB(255, 255, 0)
local TOGGLE_ON = Color3.fromRGB(255, 0, 0)
local TOGGLE_OFF = Color3.fromRGB(60, 60, 60)
local ORANGE_ACCENT = Color3.fromRGB(255, 100, 0)
local SOFT_RED = Color3.fromRGB(255, 50, 50)
local DARK_RED = Color3.fromRGB(200, 0, 0)
local ORANGE_STROKE = Color3.fromRGB(200, 80, 0)

-- UI Constants
local CORNER_RADIUS = UDim.new(0, 12)
local FONT = Enum.Font.Creepster
local BOLD_FONT = Enum.Font.GothamBold

-- Main GUI
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Parent = CoreGui
ScreenGui.Name = "ScreenGui.Name = "Vois_Hub"
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

local MainContainer = Instance.new("Frame")
MainContainer.Name = "MainContainer"
MainContainer.Position = UDim2.new(0.5, -260, 0.5, -350)
MainContainer.Parent = ScreenGui
MainContainer.BackgroundTransparency = 1
MainContainer.Size = UDim2.new(0, 520, 0, 700)

-- Title Banner
local TitleBanner = Instance.new("Frame")
TitleBanner.Name = "TitleBanner"
TitleBanner.Position = UDim2.new(0, 0, 0, 0)
TitleBanner.Parent = MainContainer
TitleBanner.Size = UDim2.new(0, 510, 0, 35)
TitleBanner.BorderSizePixel = 0
TitleBanner.BackgroundColor3 = MAIN_COLOR

-- Banner Corner
local BannerCorner = Instance.new("UICorner")
BannerCorner.CornerRadius = CORNER_RADIUS
BannerCorner.Parent = TitleBanner

-- Banner Stroke
local BannerStroke = Instance.new("UIStroke")
BannerStroke.Color = STROKE_COLOR
BannerStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
BannerStroke.Thickness = 4
BannerStroke.Parent = TitleBanner

-- Banner Gradient
local BannerGradient = Instance.new("UIGradient")
BannerGradient.Color = ColorSequence.new({
    ColorSequenceKeypoint.new(0, Color3.fromRGB(40, 10, 10)),
    ColorSequenceKeypoint.new(0.5, Color3.fromRGB(60, 15, 15)),
    ColorSequenceKeypoint.new(1, Color3.fromRGB(40, 10, 10))
})
BannerGradient.Rotation = 0
BannerGradient.Parent = TitleBanner

-- Banner Title Text
local BannerTitle = Instance.new("TextLabel")
BannerTitle.Name = "BannerTitle"
BannerTitle.TextColor3 = STROKE_COLOR
BannerTitle.TextStrokeColor3 = Color3.fromRGB(0, 0, 0)
BannerTitle.Text = "🜨 BannerTitle.Text = "🜨 Vois Hub 🜨"
BannerTitle.TextStrokeTransparency = 0.3
BannerTitle.Font = FONT
BannerTitle.Parent = TitleBanner
BannerTitle.BackgroundTransparency = 1
BannerTitle.ZIndex = 3
BannerTitle.TextSize = 22
BannerTitle.Size = UDim2.new(1, 0, 1, 0)

-- Movement Frame
local MovementFrame = Instance.new("Frame")
MovementFrame.Name = "MovementFrame"
MovementFrame.ClipsDescendants = true
MovementFrame.Position = UDim2.new(0, 0, 0, 40)
MovementFrame.Parent = MainContainer
MovementFrame.Size = UDim2.new(0, 250, 0, 660)
MovementFrame.BorderSizePixel = 0
MovementFrame.BackgroundColor3 = MAIN_COLOR

local MovementCorner = Instance.new("UICorner")
MovementCorner.CornerRadius = CORNER_RADIUS
MovementCorner.Parent = MovementFrame

local MovementStroke = Instance.new("UIStroke")
MovementStroke.Color = STROKE_COLOR
MovementStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
MovementStroke.Thickness = 4
MovementStroke.Parent = MovementFrame

-- Toxic Background
local ToxicBackground = Instance.new("Frame")
ToxicBackground.Name = "ToxicBackground"
ToxicBackground.Parent = MovementFrame
ToxicBackground.Size = UDim2.new(1, 0, 1, 0)
ToxicBackground.BorderSizePixel = 0
ToxicBackground.BackgroundColor3 = MAIN_COLOR

local ToxicCorner = Instance.new("UICorner")
ToxicCorner.CornerRadius = CORNER_RADIUS
ToxicCorner.Parent = ToxicBackground

local ToxicGradient = Instance.new("UIGradient")
ToxicGradient.Color = ColorSequence.new({
    ColorSequenceKeypoint.new(0, Color3.fromRGB(40, 10, 10)),
    ColorSequenceKeypoint.new(0.3, Color3.fromRGB(60, 15, 15)),
    ColorSequenceKeypoint.new(0.6, Color3.fromRGB(80, 20, 20)),
    ColorSequenceKeypoint.new(1, Color3.fromRGB(50, 12, 12))
})
ToxicGradient.Rotation = 90
ToxicGradient.Parent = ToxicBackground

-- Header
local Header = Instance.new("Frame")
Header.Name = "Header"
Header.Parent = MovementFrame
Header.ZIndex = 2
Header.BackgroundTransparency = 1
Header.Size = UDim2.new(1, 0, 0, 50)

-- Movement Title
local MovementTitle = Instance.new("TextLabel")
MovementTitle.Name = "Title"
MovementTitle.TextColor3 = STROKE_COLOR
MovementTitle.TextStrokeColor3 = Color3.fromRGB(0, 0, 0)
MovementTitle.Text = "🜨 MOVEMENT 🜨"
MovementTitle.TextStrokeTransparency = 0.3
MovementTitle.BackgroundTransparency = 1
MovementTitle.Font = FONT
MovementTitle.Parent = Header
MovementTitle.Position = UDim2.new(0, 12, 0, 8)
MovementTitle.TextXAlignment = Enum.TextXAlignment.Left
MovementTitle.ZIndex = 3
MovementTitle.TextSize = 18
MovementTitle.Size = UDim2.new(0, 200, 0, 22)

-- Close Button
local CloseButton = Instance.new("TextButton")
CloseButton.Name = "CloseBtn"
CloseButton.TextColor3 = Color3.new(1, 1, 1)
CloseButton.Text = "X"
CloseButton.AutoButtonColor = false
CloseButton.Font = BOLD_FONT
CloseButton.Parent = Header
CloseButton.Position = UDim2.new(1, -35, 0, 8)
CloseButton.Size = UDim2.new(0, 25, 0, 25)
CloseButton.ZIndex = 3
CloseButton.TextSize = 14
CloseButton.BackgroundColor3 = Color3.fromRGB(200, 80, 100)

local CloseButtonCorner = Instance.new("UICorner")
CloseButtonCorner.CornerRadius = UDim.new(1, 0)
CloseButtonCorner.Parent = CloseButton

local CloseButtonStroke = Instance.new("UIStroke")
CloseButtonStroke.Color = Color3.fromRGB(255, 100, 120)
CloseButtonStroke.Thickness = 2
CloseButtonStroke.Parent = CloseButton

-- Toxic Particles Generator
local function createToxicParticle(properties)
    local corner = Instance.new("UICorner")
    corner.CornerRadius = UDim.new(1, 0)
    
    local stroke = Instance.new("UIStroke")
    stroke.Color = properties.strokeColor or DARK_RED
    stroke.Transparency = 0.5
    stroke.Thickness = 1
    
    local frame = Instance.new("Frame")
    frame.BackgroundTransparency = properties.transparency or 0.5
    frame.Position = properties.position or UDim2.new(0, 0, 0, 0)
    frame.Parent = ToxicBackground
    frame.Size = UDim2.new(0, properties.size or 3, 0, properties.size or 3)
    frame.BorderSizePixel = 0
    frame.BackgroundColor3 = properties.color or STROKE_COLOR
    
    corner.Parent = frame
    stroke.Parent = frame
    
    return frame
end

-- Generate random toxic particles
local particleCount = math.random(3, 6)

-- Red particles
local redParticles = {
    {transparency = 0.56, posX = 0.79, posY = 0.72, size = 3, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.32, posX = 0.84, posY = 0.27, size = 4, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.5, posX = 0.36, posY = 0.02, size = 5, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.67, posX = 0.56, posY = 0.91, size = 3, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.58, posX = 0.1, posY = 0.39, size = 6, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.41, posX = 0.32, posY = 0.12, size = 3, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.35, posX = 0.46, posY = 0.6, size = 4, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.7, posX = 0.27, posY = 0.69, size = 5, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.31, posX = 0.56, posY = 0.64, size = 3, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.43, posX = 0.84, posY = 0.28, size = 6, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.69, posX = 0.92, posY = 0.23, size = 4, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.35, posX = 0.57, posY = 0.47, size = 5, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.48, posX = 0.26, posY = 0.64, size = 5, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.46, posX = 1.0, posY = 0.64, size = 5, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.47, posX = 0.93, posY = 0.83, size = 6, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.57, posX = 0.07, posY = 0.39, size = 4, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.32, posX = 0.83, posY = 0.09, size = 5, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.58, posX = 0.43, posY = 0.1, size = 3, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.44, posX = 0.3, posY = 0.73, size = 5, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.59, posX = 0.94, posY = 0.57, size = 6, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.7, posX = 0.15, posY = 0.96, size = 3, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.32, posX = 0.52, posY = 0.19, size = 6, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.42, posX = 0.75, posY = 0.11, size = 5, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.47, posX = 0.71, posY = 0.62, size = 3, color = STROKE_COLOR, stroke = DARK_RED},
    {transparency = 0.47, posX = 0.74, posY = 0.0, size = 5, color = STROKE_COLOR, stroke = DARK_RED},
}

-- Orange particles
local orangeParticles = {
    {transparency = 0.61, posX = 0.2, posY = 0.09, size = 5, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.46, posX = 0.57, posY = 0.15, size = 6, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.31, posX = 0.51, posY = 0.71, size = 3, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.55, posX = 0.46, posY = 0.61, size = 6, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.63, posX = 0.91, posY = 0.85, size = 5, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.34, posX = 0.97, posY = 0.46, size = 4, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.43, posX = 0.39, posY = 0.2, size = 3, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.34, posX = 0.64, posY = 0.18, size = 4, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.36, posX = 0.36, posY = 0.49, size = 4, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.52, posX = 0.21, posY = 0.47, size = 4, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.53, posX = 0.13, posY = 0.61, size = 6, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.57, posX = 0.18, posY = 0.33, size = 3, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.37, posX = 0.87, posY = 0.95, size = 4, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.68, posX = 0.69, posY = 0.76, size = 6, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.33, posX = 0.22, posY = 0.59, size = 3, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.48, posX = 0.99, posY = 0.12, size = 5, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.55, posX = 0.53, posY = 0.57, size = 6, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.64, posX = 0.67, posY = 0.45, size = 5, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
    {transparency = 0.58, posX = 0.95, posY = 0.73, size = 6, color = ORANGE_ACCENT, stroke = ORANGE_STROKE},
}

-- Create all particles
for _, data in ipairs(redParticles) do
    createToxicParticle({
        transparency = data.transparency,
        position = UDim2.new(data.posX, 0, data.posY, 0),
        size = data.size,
        color = data.color,
        strokeColor = data.stroke
    })
end

for _, data in ipairs(orangeParticles) do
    createToxicParticle({
        transparency = data.transparency,
        position = UDim2.new(data.posX, 0, data.posY, 0),
        size = data.size,
        color = data.color,
        strokeColor = data.stroke
    })
end

-- Toxic Gas Layer
local ToxicGasLayer = Instance.new("Frame")
ToxicGasLayer.Name = "ToxicGasLayer"
ToxicGasLayer.Parent = MovementFrame
ToxicGasLayer.BackgroundTransparency = 1
ToxicGasLayer.Size = UDim2.new(1, 0, 1, 0)

local GasLayerCorner = Instance.new("UICorner")
GasLayerCorner.CornerRadius = CORNER_RADIUS
GasLayerCorner.Parent = ToxicGasLayer

-- Gas cloud generator
local function createGasCloud(properties)
    local corner = Instance.new("UICorner")
    corner.CornerRadius = UDim.new(1, 0)
    
    local gradient = Instance.new("UIGradient")
    gradient.Transparency = NumberSequence.new({
        NumberSequenceKeypoint.new(0, 0.2),
        NumberSequenceKeypoint.new(0.5, 0.5),
        NumberSequenceKeypoint.new(1, 1)
    })
    
    local cloud = Instance.new("Frame")
    cloud.BackgroundTransparency = 0.75
    cloud.Position = properties.position
    cloud.Parent = ToxicGasLayer
    cloud.Size = UDim2.new(0, properties.width, 0, properties.height)
    cloud.BorderSizePixel = 0
    cloud.BackgroundColor3 = properties.color
    
    corner.Parent = cloud
    gradient.Parent = cloud
    
    return cloud
end

-- Create gas clouds
local gasClouds = {
    {posX = math.random(-20, 80) / 100, posY = 0.19, width = math.random(100, 200), height = 175, color = SOFT_RED},
    {posX = 0.28, posY = 0.52, width = 102, height = 131, color = SOFT_RED},
    {posX = 0.56, posY = 0.13, width = 148, height = 187, color = ORANGE_ACCENT},
    {posX = 0.74, posY = 0.7, width = 178, height = 161, color = SOFT_RED},
    {posX = 0.18, posY = 0.15, width = 114, height = 123, color = SOFT_RED},
    {posX = 0.51, posY = 0.71, width = 199, height = 139, color = SOFT_RED},
}

for _, cloud in ipairs(gasClouds) do
    createGasCloud({
        position = UDim2.new(cloud.posX, 0, cloud.posY, 0),
        width = cloud.width,
        height = cloud.height,
        color = cloud.color
    })
end

-- Dragging functionality
local dragging = false
local dragStart = nil
local startPos = nil

TitleBanner.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 or 
       input.UserInputType == Enum.UserInputType.Touch then
        dragging = true
        dragStart = input.Position
        startPos = MainContainer.Position
    end
end)

TitleBanner.InputChanged:Connect(function(input)
    if dragging and (input.UserInputType == Enum.UserInputType.MouseMovement or 
                     input.UserInputType == Enum.UserInputType.Touch) then
        local delta = input.Position - dragStart
        MainContainer.Position = UDim2.new(
            startPos.X.Scale, 
            startPos.X.Offset + delta.X,
            startPos.Y.Scale, 
            startPos.Y.Offset + delta.Y
        )
    end
end)

UserInputService.InputChanged:Connect(function(input)
    if dragging and (input.UserInputType == Enum.UserInputType.MouseMovement or 
                     input.UserInputType == Enum.UserInputType.Touch) then
        local delta = input.Position - dragStart
        MainContainer.Position = UDim2.new(
            startPos.X.Scale, 
            startPos.X.Offset + delta.X,
            startPos.Y.Scale, 
            startPos.Y.Offset + delta.Y
        )
    end
end)

TitleBanner.InputEnded:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 or 
       input.UserInputType == Enum.UserInputType.Touch then
        dragging = false
    end
end)

-- Close button functionality
CloseButton.MouseButton1Click:Connect(function()
    ScreenGui:Destroy()
end)
