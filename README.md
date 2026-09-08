local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local UserInputService = game:GetService("UserInputService")
local Lighting = game:GetService("Lighting")
local LocalPlayer = Players.LocalPlayer
local Camera = workspace.CurrentCamera

local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "TeamJakr"
ScreenGui.ResetOnSpawn = false
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
ScreenGui.DisplayOrder = 2147483647
ScreenGui.Parent = LocalPlayer:WaitForChild("PlayerGui")

local ToggleButton = Instance.new("TextButton")
ToggleButton.Size = UDim2.new(0, 65, 0, 65)
ToggleButton.Position = UDim2.new(0, 20, 0, 200)
ToggleButton.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
ToggleButton.BorderSizePixel = 0
ToggleButton.Font = Enum.Font.GothamBlack
ToggleButton.Text = "JK"
ToggleButton.TextColor3 = Color3.fromRGB(255, 255, 255)
ToggleButton.TextSize = 22
ToggleButton.ZIndex = 2147483647
ToggleButton.Active = true
ToggleButton.Draggable = true
ToggleButton.Parent = ScreenGui

local ToggleStroke = Instance.new("UIStroke")
ToggleStroke.Thickness = 2
ToggleStroke.Color = Color3.fromRGB(100, 100, 100)
ToggleStroke.Parent = ToggleButton

local ToggleCorner = Instance.new("UICorner")
ToggleCorner.CornerRadius = UDim.new(0, 20)
ToggleCorner.Parent = ToggleButton

local MainFrame = Instance.new("Frame")
MainFrame.Size = UDim2.new(0, 280, 0, 400)
MainFrame.Position = UDim2.new(0.5, -140, 0.5, -200)
MainFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
MainFrame.BorderSizePixel = 0
MainFrame.Active = true
MainFrame.Draggable = true
MainFrame.ZIndex = 2147483646
MainFrame.Visible = false
MainFrame.Parent = ScreenGui

local MainCorner = Instance.new("UICorner")
MainCorner.CornerRadius = UDim.new(0, 16)
MainCorner.Parent = MainFrame

local MainStroke = Instance.new("UIStroke")
MainStroke.Thickness = 1
MainStroke.Color = Color3.fromRGB(60, 60, 60)
MainStroke.Parent = MainFrame

local TitleBar = Instance.new("Frame")
TitleBar.Size = UDim2.new(1, 0, 0, 55)
TitleBar.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
TitleBar.BorderSizePixel = 0
TitleBar.ZIndex = 2147483647
TitleBar.Parent = MainFrame

local TitleBarCorner = Instance.new("UICorner")
TitleBarCorner.CornerRadius = UDim.new(0, 16)
TitleBarCorner.Parent = TitleBar

local Title = Instance.new("TextLabel")
Title.Size = UDim2.new(1, -50, 0, 30)
Title.Position = UDim2.new(0, 15, 0, 8)
Title.BackgroundTransparency = 1
Title.Font = Enum.Font.GothamBlack
Title.Text = "TEAM JAKR"
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.TextSize = 20
Title.TextXAlignment = Enum.TextXAlignment.Left
Title.ZIndex = 2147483647
Title.Parent = TitleBar

local SubTitle = Instance.new("TextLabel")
SubTitle.Size = UDim2.new(1, -50, 0, 15)
SubTitle.Position = UDim2.new(0, 15, 0, 35)
SubTitle.BackgroundTransparency = 1
SubTitle.Font = Enum.Font.Gotham
SubTitle.Text = "PREMIUM SCRIPT"
SubTitle.TextColor3 = Color3.fromRGB(130, 130, 130)
SubTitle.TextSize = 9
SubTitle.TextXAlignment = Enum.TextXAlignment.Left
SubTitle.ZIndex = 2147483647
SubTitle.Parent = TitleBar

local CloseButton = Instance.new("TextButton")
CloseButton.Size = UDim2.new(0, 30, 0, 30)
CloseButton.Position = UDim2.new(1, -40, 0, 12)
CloseButton.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
CloseButton.BorderSizePixel = 0
CloseButton.Font = Enum.Font.GothamBold
CloseButton.Text = "X"
CloseButton.TextColor3 = Color3.fromRGB(255, 255, 255)
CloseButton.TextSize = 16
CloseButton.ZIndex = 2147483647
CloseButton.Parent = TitleBar

local CloseCorner = Instance.new("UICorner")
CloseCorner.CornerRadius = UDim.new(0, 10)
CloseCorner.Parent = CloseButton

local function createButton(name, position, icon)
    local btn = Instance.new("TextButton")
    btn.Size = UDim2.new(1, -30, 0, 38)
    btn.Position = UDim2.new(0, 15, 0, position)
    btn.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
    btn.BorderSizePixel = 0
    btn.Font = Enum.Font.GothamBold
    btn.Text = icon .. " " .. name
    btn.TextColor3 = Color3.fromRGB(255, 255, 255)
    btn.TextSize = 12
    btn.ZIndex = 2147483647
    btn.Parent = MainFrame
    
    local corner = Instance.new("UICorner")
    corner.CornerRadius = UDim.new(0, 12)
    corner.Parent = btn
    
    local stroke = Instance.new("UIStroke")
    stroke.Thickness = 1
    stroke.Color = Color3.fromRGB(50, 50, 50)
    stroke.Parent = btn
    
    return btn
end

local AimbotButton = createButton("Aimbot: OFF", 65, "🎯")
local WallCheckButton = createButton("WallCheck: ON", 106, "🧱")
local ESPButton = createButton("ESP: OFF", 147, "👁")
local RainbowButton = createButton("Rainbow: OFF", 188, "🌈")
local NightButton = createButton("Night: OFF", 229, "🌙")
local DayButton = createButton("Day: OFF", 270, "☀️")

local ThemeButton = Instance.new("TextButton")
ThemeButton.Size = UDim2.new(1, -30, 0, 40)
ThemeButton.Position = UDim2.new(0, 15, 0, 315)
ThemeButton.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
ThemeButton.BorderSizePixel = 0
ThemeButton.Font = Enum.Font.GothamBlack
ThemeButton.Text = "🎨 Theme: BLACK"
ThemeButton.TextColor3 = Color3.fromRGB(255, 255, 255)
ThemeButton.TextSize = 13
ThemeButton.ZIndex = 2147483647
ThemeButton.Parent = MainFrame

local ThemeCorner = Instance.new("UICorner")
ThemeCorner.CornerRadius = UDim.new(0, 12)
ThemeCorner.Parent = ThemeButton

local ThemeStroke = Instance.new("UIStroke")
ThemeStroke.Thickness = 1
ThemeStroke.Color = Color3.fromRGB(50, 50, 50)
ThemeStroke.Parent = ThemeButton

local aimbotEnabled = false
local wallCheckEnabled = true
local espEnabled = false
local rainbowEnabled = false
local nightEnabled = false
local dayEnabled = false
local blackTheme = true
local target = nil
local espObjects = {}
local isDead = false
local rainbowTick = 0
local rainbowSpeed = 0.002

local function getRainbowColor()
    rainbowTick = rainbowTick + rainbowSpeed
    if rainbowTick > 1 then
        rainbowTick = 0
    end
    
    local r = math.sin(rainbowTick * math.pi * 2) * 127 + 128
    local g = math.sin((rainbowTick + 0.33) * math.pi * 2) * 127 + 128
    local b = math.sin((rainbowTick + 0.67) * math.pi * 2) * 127 + 128
    
    return Color3.fromRGB(math.floor(r), math.floor(g), math.floor(b))
end

local function applyTheme()
    local frameBg, titleBg, btnBg, textColor, strokeColor, subColor
    
    if blackTheme then
        frameBg = Color3.fromRGB(20, 20, 20)
        titleBg = Color3.fromRGB(25, 25, 25)
        btnBg = Color3.fromRGB(30, 30, 30)
        textColor = Color3.fromRGB(255, 255, 255)
        strokeColor = Color3.fromRGB(50, 50, 50)
        subColor = Color3.fromRGB(130, 130, 130)
    else
        frameBg = Color3.fromRGB(235, 235, 235)
        titleBg = Color3.fromRGB(220, 220, 220)
        btnBg = Color3.fromRGB(245, 245, 245)
        textColor = Color3.fromRGB(0, 0, 0)
        strokeColor = Color3.fromRGB(180, 180, 180)
        subColor = Color3.fromRGB(100, 100, 100)
    end
    
    MainFrame.BackgroundColor3 = frameBg
    MainStroke.Color = strokeColor
    TitleBar.BackgroundColor3 = titleBg
    Title.TextColor3 = textColor
    SubTitle.TextColor3 = subColor
    ToggleButton.BackgroundColor3 = frameBg
    ToggleButton.TextColor3 = textColor
    ToggleStroke.Color = strokeColor
    
    local buttons = {AimbotButton, WallCheckButton, ESPButton, RainbowButton, NightButton, DayButton, ThemeButton}
    
    for _, btn in pairs(buttons) do
        if btn.BackgroundColor3 == Color3.fromRGB(0, 150, 0) then
            btn.BackgroundColor3 = Color3.fromRGB(0, 150, 0)
        else
            btn.BackgroundColor3 = btnBg
        end
        btn.TextColor3 = textColor
        
        for _, child in pairs(btn:GetChildren()) do
            if child:IsA("UIStroke") then
                child.Color = strokeColor
            end
        end
    end
    
    ThemeButton.Text = blackTheme and "🎨 Theme: BLACK" or "🎨 Theme: WHITE"
end

local function isPlayerAlive(player)
    local character = player.Character
    if not character then return false end
    local humanoid = character:FindFirstChild("Humanoid")
    if not humanoid then return false end
    return humanoid.Health > 0
end

local function canSeeTarget(targetHead)
    local origin = Camera.CFrame.Position
    local direction = (targetHead.Position - origin).Unit * 1000
    
    local raycastParams = RaycastParams.new()
    raycastParams.FilterType = Enum.RaycastFilterType.Blacklist
    raycastParams.FilterDescendantsInstances = {LocalPlayer.Character}
    
    local raycastResult = workspace:Raycast(origin, direction, raycastParams)
    
    if raycastResult then
        local hitInstance = raycastResult.Instance
        local targetCharacter = targetHead.Parent
        
        if hitInstance:IsDescendantOf(targetCharacter) then
            return true
        end
    end
    
    return false
end

local function isTargetValid(player)
    if not player then return false end
    if player == LocalPlayer then return false end
    if not isPlayerAlive(player) then return false end
    
    local character = player.Character
    local head = character and character:FindFirstChild("Head")
    if not head then return false end
    
    if wallCheckEnabled then
        return canSeeTarget(head)
    end
    
    return true
end

local function getClosestPlayer()
    if isDead or not aimbotEnabled then return nil end
    
    if target and isTargetValid(target) then
        return target
    end
    
    local closest = nil
    local shortestDistance = math.huge
    
    for _, player in ipairs(Players:GetPlayers()) do
        if isTargetValid(player) then
            local character = player.Character
            local head = character:FindFirstChild("Head")
            
            if head then
                local rootPart = LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("HumanoidRootPart")
                
                if rootPart then
                    local distance = (rootPart.Position - head.Position).Magnitude
                    
                    if distance < shortestDistance then
                        shortestDistance = distance
                        closest = player
                    end
                end
            end
        end
    end
    
    return closest
end

local function createBoxESP(player)
    local character = player.Character
    if not character then return end
    
    local humanoid = character:FindFirstChild("Humanoid")
    local head = character:FindFirstChild("Head")
    local rootPart = character:FindFirstChild("HumanoidRootPart")
    if not humanoid or not head or not rootPart then return end
    
    local boxOutline = Drawing.new("Square")
    boxOutline.Thickness = 3
    boxOutline.Filled = false
    boxOutline.Color = blackTheme and Color3.fromRGB(255, 255, 255) or Color3.fromRGB(0, 0, 0)
    boxOutline.Transparency = 1
    boxOutline.Visible = false
    
    local boxFill = Drawing.new("Square")
    boxFill.Thickness = 1
    boxFill.Filled = true
    boxFill.Color = blackTheme and Color3.fromRGB(0, 0, 0) or Color3.fromRGB(255, 255, 255)
    boxFill.Transparency = 0.7
    boxFill.Visible = false
    
    local nameText = Drawing.new("Text")
    nameText.Size = 13
    nameText.Center = true
    nameText.Outline = true
    nameText.Color = blackTheme and Color3.fromRGB(255, 255, 255) or Color3.fromRGB(0, 0, 0)
    nameText.Visible = false
    
    local healthText = Drawing.new("Text")
    healthText.Size = 12
    healthText.Center = true
    healthText.Outline = true
    healthText.Color = Color3.fromRGB(0, 255, 0)
    healthText.Visible = false
    
    local healthBarOutline = Drawing.new("Square")
    healthBarOutline.Thickness = 2
    healthBarOutline.Filled = false
    healthBarOutline.Color = blackTheme and Color3.fromRGB(255, 255, 255) or Color3.fromRGB(0, 0, 0)
    healthBarOutline.Transparency = 1
    healthBarOutline.Visible = false
    
    local healthBarBackground = Drawing.new("Square")
    healthBarBackground.Thickness = 1
    healthBarBackground.Filled = true
    healthBarBackground.Color = Color3.fromRGB(255, 0, 0)
    healthBarBackground.Transparency = 1
    healthBarBackground.Visible = false
    
    local healthBarFill = Drawing.new("Square")
    healthBarFill.Thickness = 1
    healthBarFill.Filled = true
    healthBarFill.Color = Color3.fromRGB(0, 255, 0)
    healthBarFill.Transparency = 1
    healthBarFill.Visible = false
    
    local espData = {
        boxOutline = boxOutline,
        boxFill = boxFill,
        nameText = nameText,
        healthText = healthText,
        healthBarOutline = healthBarOutline,
        healthBarBackground = healthBarBackground,
        healthBarFill = healthBarFill,
        player = player,
        isActive = true
    }
    
    espObjects[player] = espData
    
    local function updateBox()
        local currentChar = player.Character
        
        if not currentChar or not currentChar.Parent or not isPlayerAlive(player) then
            boxOutline.Visible = false
            boxFill.Visible = false
            nameText.Visible = false
            healthText.Visible = false
            healthBarOutline.Visible = false
            healthBarBackground.Visible = false
            healthBarFill.Visible = false
            espData.isActive = false
            return
        end
        
        local currentHumanoid = currentChar:FindFirstChild("Humanoid")
        local currentHead = currentChar:FindFirstChild("Head")
        local currentRoot = currentChar:FindFirstChild("HumanoidRootPart")
        
        if not currentHumanoid or not currentHead or not currentRoot then
            boxOutline.Visible = false
            boxFill.Visible = false
            nameText.Visible = false
            healthText.Visible = false
            healthBarOutline.Visible = false
            healthBarBackground.Visible = false
            healthBarFill.Visible = false
            espData.isActive = false
            return
        end
        
        if currentHumanoid.Health <= 0 then
            boxOutline.Visible = false
            boxFill.Visible = false
            nameText.Visible = false
            healthText.Visible = false
            healthBarOutline.Visible = false
            healthBarBackground.Visible = false
            healthBarFill.Visible = false
            espData.isActive = false
            return
        end
        
        espData.isActive = true
        
        local rootPos, rootOnScreen = Camera:WorldToViewportPoint(currentRoot.Position)
        local headPos, headOnScreen = Camera:WorldToViewportPoint(currentHead.Position + Vector3.new(0, 0.5, 0))
        
        if rootOnScreen and headOnScreen then
            local height = math.abs(headPos.Y - rootPos.Y) * 1.4
            local width = height * 0.45
            
            local boxX = rootPos.X - width / 2
            local boxY = headPos.Y - height * 0.15
            local boxWidth = width
            local boxHeight = height
            
            boxOutline.Position = Vector2.new(boxX, boxY)
            boxOutline.Size = Vector2.new(boxWidth, boxHeight)
            boxOutline.Visible = true
            
            boxFill.Position = Vector2.new(boxX, boxY)
            boxFill.Size = Vector2.new(boxWidth, boxHeight)
            boxFill.Visible = true
            
            nameText.Text = player.Name
            nameText.Position = Vector2.new(rootPos.X, boxY - 20)
            nameText.Visible = true
            
            local health = math.floor(currentHumanoid.Health)
            local maxHealth = currentHumanoid.MaxHealth
            healthText.Text = "HP: " .. health .. " / " .. maxHealth
            
            if health > 50 then
                healthText.Color = Color3.fromRGB(0, 255, 0)
            elseif health > 25 then
                healthText.Color = Color3.fromRGB(255, 255, 0)
            else
                healthText.Color = Color3.fromRGB(255, 0, 0)
            end
            
            healthText.Position = Vector2.new(rootPos.X, boxY + boxHeight + 5)
            healthText.Visible = true
            
            local barWidth = boxWidth
            local barHeight = 4
            local barX = boxX
            local barY = boxY + boxHeight + 25
            
            healthBarOutline.Position = Vector2.new(barX - 1, barY - 1)
            healthBarOutline.Size = Vector2.new(barWidth + 2, barHeight + 2)
            healthBarOutline.Visible = true
            
            healthBarBackground.Position = Vector2.new(barX, barY)
            healthBarBackground.Size = Vector2.new(barWidth, barHeight)
            healthBarBackground.Visible = true
            
            local healthPercent = math.clamp(health / maxHealth, 0, 1)
            local fillWidth = math.max(0, barWidth * healthPercent)
            
            healthBarFill.Position = Vector2.new(barX, barY)
            healthBarFill.Size = Vector2.new(fillWidth, barHeight)
            healthBarFill.Visible = true
            
            if healthPercent > 0.5 then
                healthBarFill.Color = Color3.fromRGB(0, 255, 0)
            elseif healthPercent > 0.25 then
                healthBarFill.Color = Color3.fromRGB(255, 255, 0)
            else
                healthBarFill.Color = Color3.fromRGB(255, 0, 0)
            end
            
            if rainbowEnabled then
                local rainbowColor = getRainbowColor()
                boxOutline.Color = rainbowColor
                nameText.Color = rainbowColor
                healthBarOutline.Color = rainbowColor
            end
        else
            boxOutline.Visible = false
            boxFill.Visible = false
            nameText.Visible = false
            healthText.Visible = false
            healthBarOutline.Visible = false
            healthBarBackground.Visible = false
            healthBarFill.Visible = false
        end
    end
    
    local connection = RunService.RenderStepped:Connect(updateBox)
    espData.connection = connection
end

local function clearESP(player)
    if espObjects[player] then
        local objects = espObjects[player]
        if objects.connection then
            objects.connection:Disconnect()
        end
        if objects.boxOutline then objects.boxOutline:Remove() end
        if objects.boxFill then objects.boxFill:Remove() end
        if objects.nameText then objects.nameText:Remove() end
        if objects.healthText then objects.healthText:Remove() end
        if objects.healthBarOutline then objects.healthBarOutline:Remove() end
        if objects.healthBarBackground then objects.healthBarBackground:Remove() end
        if objects.healthBarFill then objects.healthBarFill:Remove() end
        espObjects[player] = nil
    end
end

local function clearAllESP()
    for player, _ in pairs(espObjects) do
        clearESP(player)
    end
end

local function checkAndCreateESP()
    if not espEnabled then return end
    
    for _, player in ipairs(Players:GetPlayers()) do
        if player ~= LocalPlayer then
            local character = player.Character
            local humanoid = character and character:FindFirstChild("Humanoid")
            
            if isPlayerAlive(player) and humanoid then
                if not espObjects[player] then
                    createBoxESP(player)
                else
                    local espData = espObjects[player]
                    if not espData.isActive then
                        clearESP(player)
                        createBoxESP(player)
                    end
                end
            else
                if espObjects[player] and espObjects[player].isActive then
                    espObjects[player].boxOutline.Visible = false
                    espObjects[player].boxFill.Visible = false
                    espObjects[player].nameText.Visible = false
                    espObjects[player].healthText.Visible = false
                    espObjects[player].healthBarOutline.Visible = false
                    espObjects[player].healthBarBackground.Visible = false
                    espObjects[player].healthBarFill.Visible = false
                    espObjects[player].isActive = false
                end
            end
        end
    end
end

local function checkDeath()
    local character = LocalPlayer.Character
    if character then
        local humanoid = character:FindFirstChild("Humanoid")
        if humanoid then
            isDead = humanoid.Health <= 0
        end
    else
        isDead = true
    end
end

local function startESP()
    checkAndCreateESP()
    task.spawn(function()
        while espEnabled do
            task.wait(1)
            checkAndCreateESP()
        end
    end)
end

local function applyNight()
    Lighting.Brightness = 0.1
    Lighting.ClockTime = 0
    Lighting.FogEnd = 100
    Lighting.Ambient = Color3.fromRGB(20, 20, 40)
end

local function applyDay()
    Lighting.Brightness = 2
    Lighting.ClockTime = 14
    Lighting.FogEnd = 1000
    Lighting.Ambient = Color3.fromRGB(255, 255, 255)
end

local function applyRainbowToUI()
    if rainbowEnabled then
        local rainbowColor = getRainbowColor()
        MainStroke.Color = rainbowColor
        Title.TextColor3 = rainbowColor
        ToggleStroke.Color = rainbowColor
        ToggleButton.TextColor3 = rainbowColor
        ThemeButton.TextColor3 = rainbowColor
        RainbowButton.TextColor3 = rainbowColor
    end
end

LocalPlayer.CharacterAdded:Connect(function(character)
    isDead = false
    local humanoid = character:WaitForChild("Humanoid")
    humanoid.Died:Connect(function()
        isDead = true
        target = nil
    end)
    
    if espEnabled then
        task.wait(0.1)
        checkAndCreateESP()
    end
    
    if aimbotEnabled then
        task.wait(0.1)
        target = getClosestPlayer()
    end
end)

ToggleButton.MouseButton1Click:Connect(function()
    MainFrame.Visible = not MainFrame.Visible
end)

CloseButton.MouseButton1Click:Connect(function()
    MainFrame.Visible = false
end)

AimbotButton.MouseButton1Click:Connect(function()
    aimbotEnabled = not aimbotEnabled
    if aimbotEnabled then
        AimbotButton.Text = "🎯 Aimbot: ON"
        AimbotButton.BackgroundColor3 = Color3.fromRGB(0, 150, 0)
        target = getClosestPlayer()
    else
        AimbotButton.Text = "🎯 Aimbot: OFF"
        AimbotButton.BackgroundColor3 = blackTheme and Color3.fromRGB(30, 30, 30) or Color3.fromRGB(245, 245, 245)
        target = nil
    end
end)

WallCheckButton.MouseButton1Click:Connect(function()
    wallCheckEnabled = not wallCheckEnabled
    if wallCheckEnabled then
        WallCheckButton.Text = "🧱 WallCheck: ON"
        WallCheckButton.BackgroundColor3 = Color3.fromRGB(0, 150, 0)
    else
        WallCheckButton.Text = "🧱 WallCheck: OFF"
        WallCheckButton.BackgroundColor3 = blackTheme and Color3.fromRGB(30, 30, 30) or Color3.fromRGB(245, 245, 245)
    end
end)

ESPButton.MouseButton1Click:Connect(function()
    espEnabled = not espEnabled
    if espEnabled then
        ESPButton.Text = "👁 ESP: ON"
        ESPButton.BackgroundColor3 = Color3.fromRGB(0, 150, 0)
        startESP()
    else
        ESPButton.Text = "👁 ESP: OFF"
        ESPButton.BackgroundColor3 = blackTheme and Color3.fromRGB(30, 30, 30) or Color3.fromRGB(245, 245, 245)
        clearAllESP()
    end
end)

RainbowButton.MouseButton1Click:Connect(function()
    rainbowEnabled = not rainbowEnabled
    if rainbowEnabled then
        RainbowButton.Text = "🌈 Rainbow: ON"
        RainbowButton.BackgroundColor3 = Color3.fromRGB(0, 150, 0)
    else
        RainbowButton.Text = "🌈 Rainbow: OFF"
        RainbowButton.BackgroundColor3 = blackTheme and Color3.fromRGB(30, 30, 30) or Color3.fromRGB(245, 245, 245)
        applyTheme()
    end
end)

NightButton.MouseButton1Click:Connect(function()
    nightEnabled = not nightEnabled
    if nightEnabled then
        nightEnabled = true
        dayEnabled = false
        NightButton.Text = "🌙 Night: ON"
        NightButton.BackgroundColor3 = Color3.fromRGB(0, 150, 0)
        DayButton.Text = "☀️ Day: OFF"
        DayButton.BackgroundColor3 = blackTheme and Color3.fromRGB(30, 30, 30) or Color3.fromRGB(245, 245, 245)
        applyNight()
    else
        nightEnabled = false
        NightButton.Text = "🌙 Night: OFF"
        NightButton.BackgroundColor3 = blackTheme and Color3.fromRGB(30, 30, 30) or Color3.fromRGB(245, 245, 245)
        applyDay()
    end
end)

DayButton.MouseButton1Click:Connect(function()
    dayEnabled = not dayEnabled
    if dayEnabled then
        dayEnabled = true
        nightEnabled = false
        DayButton.Text = "☀️ Day: ON"
        DayButton.BackgroundColor3 = Color3.fromRGB(0, 150, 0)
        NightButton.Text = "🌙 Night: OFF"
        NightButton.BackgroundColor3 = blackTheme and Color3.fromRGB(30, 30, 30) or Color3.fromRGB(245, 245, 245)
        applyDay()
    else
        dayEnabled = false
        DayButton.Text = "☀️ Day: OFF"
        DayButton.BackgroundColor3 = blackTheme and Color3.fromRGB(30, 30, 30) or Color3.fromRGB(245, 245, 245)
        applyDay()
    end
end)

ThemeButton.MouseButton1Click:Connect(function()
    blackTheme = not blackTheme
    applyTheme()
end)

Players.PlayerAdded:Connect(function(player)
    if espEnabled then
        player.CharacterAdded:Connect(function(character)
            if espEnabled then
                task.wait(0.1)
                checkAndCreateESP()
            end
        end)
    end
    
    if aimbotEnabled and player ~= LocalPlayer then
        player.CharacterAdded:Connect(function(character)
            if aimbotEnabled and not isDead then
                task.wait(0.1)
                if not target or not isTargetValid(target) then
                    target = getClosestPlayer()
                end
            end
        end)
    end
end)

Players.PlayerRemoving:Connect(function(player)
    clearESP(player)
    if target == player then
        target = nil
    end
end)

RunService.RenderStepped:Connect(function()
    checkDeath()
    applyRainbowToUI()
    
    if aimbotEnabled and not isDead then
        if target and isTargetValid(target) then
            local head = target.Character:FindFirstChild("Head")
            
            if head then
                Camera.CFrame = CFrame.new(Camera.CFrame.Position, head.Position)
            end
        else
            target = getClosestPlayer()
        end
    elseif isDead then
        target = nil
    end
end)

UserInputService.InputBegan:Connect(function(input, gameProcessed)
    if input.UserInputType == Enum.UserInputType.Touch then
        checkDeath()
        
        if aimbotEnabled and not isDead and target and isTargetValid(target) then
            local head = target.Character:FindFirstChild("Head")
            if head then
                Camera.CFrame = CFrame.new(Camera.CFrame.Position, head.Position)
            end
        end
    end
end)
