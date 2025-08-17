-- vitin aimbot - TeamCheck robusto, ESP fix, wallcheck compatível, créditos em portugues, minimizador, confirmacao fechar, toggle corrigido
-- SEM ACENTO OU CEDILHA EM NOMES/FUNCOES/ABAS/BOTOES
-- AIMBOT FUNCIONA COM ARMA NA MAO (usa Head ou HumanoidRootPart como alvo)

local KEY_CORRECT = "vitin"

pcall(function() game.CoreGui.FullScriptLoader:Destroy() end)
local gui = Instance.new("ScreenGui", game.CoreGui)
gui.Name = "FullScriptLoader"

local loader = Instance.new("Frame", gui)
loader.Size = UDim2.new(0, 600, 0, 420)
loader.Position = UDim2.new(0.5, -300, 0.5, -210)
loader.BackgroundColor3 = Color3.fromRGB(25,25,35)
loader.Active = true
loader.Draggable = true

local title = Instance.new("TextLabel", loader)
title.Size = UDim2.new(1, 0, 0, 38)
title.BackgroundTransparency = 1
title.Text = "vitin aimbot"
title.TextColor3 = Color3.new(1,1,1)
title.Font = Enum.Font.SourceSansBold
title.TextSize = 34

local keyLabel = Instance.new("TextLabel", loader)
keyLabel.Size = UDim2.new(1, -40, 0, 20)
keyLabel.Position = UDim2.new(0, 20, 0, 60)
keyLabel.BackgroundTransparency = 1
keyLabel.Text = "Digite sua KEY abaixo:"
keyLabel.TextColor3 = Color3.fromRGB(200,200,255)
keyLabel.Font = Enum.Font.SourceSans
keyLabel.TextSize = 18

local keyBox = Instance.new("TextBox", loader)
keyBox.Size = UDim2.new(1, -40, 0, 36)
keyBox.Position = UDim2.new(0, 20, 0, 90)
keyBox.PlaceholderText = "Digite sua key aqui"
keyBox.BackgroundColor3 = Color3.fromRGB(35,35,45)
keyBox.TextColor3 = Color3.new(1,1,1)
keyBox.Font = Enum.Font.SourceSans
keyBox.TextSize = 20

local info = Instance.new("TextLabel", loader)
info.Size = UDim2.new(1, -40, 0, 18)
info.Position = UDim2.new(0, 20, 0, 130)
info.BackgroundTransparency = 1
info.Text = ""
info.TextColor3 = Color3.fromRGB(255,100,100)
info.Font = Enum.Font.SourceSans
info.TextSize = 16

local btn = Instance.new("TextButton", loader)
btn.Size = UDim2.new(0, 140, 0, 38)
btn.Position = UDim2.new(0.5, -70, 0, 170)
btn.Text = "ENTRAR"
btn.BackgroundColor3 = Color3.fromRGB(60,110,210)
btn.TextColor3 = Color3.new(1,1,1)
btn.Font = Enum.Font.SourceSansBold
btn.TextSize = 22

local function showInfo(txt, color)
    info.Text = txt
    info.TextColor3 = color or Color3.fromRGB(255,100,100)
end

btn.MouseButton1Click:Connect(function()
    local key = keyBox.Text
    if key == KEY_CORRECT then
        showInfo("Carregando painel...", Color3.fromRGB(100,255,100))
        wait(0.5)
        loader.Visible = false
        gui.FullScriptMain.Visible = true
    else
        showInfo("KEY incorreta!", Color3.fromRGB(255,100,100))
    end
end)

------------------- MAIN GUI -------------------
local main = Instance.new("Frame", gui)
main.Name = "FullScriptMain"
main.Visible = false
main.Size = UDim2.new(0, 600, 0, 420)
main.Position = UDim2.new(0.5, -300, 0.5, -210)
main.BackgroundColor3 = Color3.fromRGB(32,32,36)
main.Active = true
main.Draggable = true

-- Topbar
local topbar = Instance.new("TextLabel", main)
topbar.Size = UDim2.new(1, -80, 0, 38)
topbar.Position = UDim2.new(0, 0, 0, 0)
topbar.BackgroundTransparency = 1
topbar.Text = "vitin aimbot"
topbar.Font = Enum.Font.SourceSansBold
topbar.TextColor3 = Color3.new(1,1,1)
topbar.TextSize = 30

-- Minimize Button
local minimizeBtn = Instance.new("TextButton", main)
minimizeBtn.Size = UDim2.new(0, 32, 0, 32)
minimizeBtn.Position = UDim2.new(1, -70, 0, 3)
minimizeBtn.BackgroundColor3 = Color3.fromRGB(45,45,45)
minimizeBtn.Text = "-"
minimizeBtn.Font = Enum.Font.SourceSansBold
minimizeBtn.TextSize = 30
minimizeBtn.TextColor3 = Color3.new(1,1,1)
minimizeBtn.BorderSizePixel = 0

-- Close Button
local closeBtn = Instance.new("TextButton", main)
closeBtn.Size = UDim2.new(0, 32, 0, 32)
closeBtn.Position = UDim2.new(1, -35, 0, 3)
closeBtn.BackgroundColor3 = Color3.fromRGB(90,30,30)
closeBtn.Text = "X"
closeBtn.Font = Enum.Font.SourceSansBold
closeBtn.TextSize = 22
closeBtn.TextColor3 = Color3.new(1,1,1)
closeBtn.BorderSizePixel = 0

-- Confirm Close Panel
local confirmClose = Instance.new("Frame", gui)
confirmClose.Size = UDim2.new(0, 320, 0, 140)
confirmClose.Position = UDim2.new(0.5, -160, 0.5, -70)
confirmClose.BackgroundColor3 = Color3.fromRGB(40,40,40)
confirmClose.Visible = false

local confirmLabel = Instance.new("TextLabel", confirmClose)
confirmLabel.Size = UDim2.new(1, 0, 0, 54)
confirmLabel.Position = UDim2.new(0,0,0,5)
confirmLabel.BackgroundTransparency = 1
confirmLabel.Text = "Tem certeza que deseja fechar o painel?"
confirmLabel.TextColor3 = Color3.new(1,1,1)
confirmLabel.Font = Enum.Font.SourceSansBold
confirmLabel.TextSize = 20

local confirmYes = Instance.new("TextButton", confirmClose)
confirmYes.Size = UDim2.new(0, 120, 0, 38)
confirmYes.Position = UDim2.new(0, 35, 0, 70)
confirmYes.BackgroundColor3 = Color3.fromRGB(60,160,75)
confirmYes.Text = "Sim"
confirmYes.Font = Enum.Font.SourceSansBold
confirmYes.TextSize = 22
confirmYes.TextColor3 = Color3.new(1,1,1)
confirmYes.BorderSizePixel = 0

local confirmNo = Instance.new("TextButton", confirmClose)
confirmNo.Size = UDim2.new(0, 120, 0, 38)
confirmNo.Position = UDim2.new(1, -155, 0, 70)
confirmNo.BackgroundColor3 = Color3.fromRGB(160,60,60)
confirmNo.Text = "Nao"
confirmNo.Font = Enum.Font.SourceSansBold
confirmNo.TextSize = 22
confirmNo.TextColor3 = Color3.new(1,1,1)
confirmNo.BorderSizePixel = 0

closeBtn.MouseButton1Click:Connect(function()
    main.Visible = false
    confirmClose.Visible = true
end)
confirmNo.MouseButton1Click:Connect(function()
    confirmClose.Visible = false
    main.Visible = true
end)
confirmYes.MouseButton1Click:Connect(function()
    gui:Destroy()
end)

-- Minimize logic
minimizeBtn.MouseButton1Click:Connect(function()
    main.Visible = false
end)
game:GetService("UserInputService").InputBegan:Connect(function(input, gp)
    if input.KeyCode == Enum.KeyCode.LeftControl or input.KeyCode == Enum.KeyCode.RightControl then
        if not main.Visible and not loader.Visible and not confirmClose.Visible then
            main.Visible = true
        end
    end
end)

-- Tabs
local tabNames = {"Main", "ESP", "Visual", "Otimizacao", "Creditos"}
local tabFrames, tabBtns = {}, {}
for i,tab in ipairs(tabNames) do
    local b = Instance.new("TextButton", main)
    b.Size = UDim2.new(0, 110, 0, 36)
    b.Position = UDim2.new(0, 20+((i-1)*115), 0, 45)
    b.Text = tab
    b.Name = tab.."Tab"
    b.BackgroundColor3 = Color3.fromRGB(44,44,48)
    b.TextColor3 = Color3.new(1,1,1)
    b.Font = Enum.Font.SourceSansBold
    b.TextSize = 20
    tabBtns[tab] = b

    local f = Instance.new("Frame", main)
    f.Size = UDim2.new(1, -40, 1, -95)
    f.Position = UDim2.new(0, 20, 0, 90)
    f.BackgroundTransparency = 1
    f.Visible = (i==1)
    tabFrames[tab] = f

    b.MouseButton1Click:Connect(function()
        for _,n in ipairs(tabNames) do tabFrames[n].Visible = false; tabBtns[n].BackgroundColor3 = Color3.fromRGB(44,44,48) end
        f.Visible = true
        b.BackgroundColor3 = Color3.fromRGB(64,64,78)
    end)
    if i==1 then b.BackgroundColor3 = Color3.fromRGB(64,64,78) end
end

-- GLOBAL STATE
local UIS = game:GetService("UserInputService")
local RunService = game:GetService("RunService")
local Players = game:GetService("Players")
local Lighting = game:GetService("Lighting")
local LP = Players.LocalPlayer

local state = {
    -- MAIN
    AimbotActive=false,
    TeamCheck=false,
    WallCheck=false,
    FOV=100,
    HoldType="Mouse2",
    HoldKey=Enum.KeyCode.Q,
    -- ESP
    ESPActive = false,
    ESPTeamCheck = true,
    ESPColor = Color3.new(1,0,0),
    -- VISUAL
    RainbowFOV = false,
    FOVColor = Color3.fromRGB(0,120,255),
    SlowMotion = false,
    SmoothSky = false,
    -- OTIMIZACAO
    FPSUnlock = false,
}

local fovMin, fovMax = 40, 295

-- SWITCH
local function addSwitch(parent, y, label, default, callback)
    local text = Instance.new("TextLabel", parent)
    text.Size = UDim2.new(0.6, 0, 0, 32)
    text.Position = UDim2.new(0, 30, 0, y)
    text.Text = label
    text.Font = Enum.Font.SourceSans
    text.TextSize = 20
    text.BackgroundTransparency = 1
    text.TextColor3 = Color3.new(1,1,1)

    local toggle = Instance.new("TextButton", parent)
    toggle.Size = UDim2.new(0, 48, 0, 28)
    toggle.Position = UDim2.new(0.7, 0, 0, y+2)
    toggle.BackgroundColor3 = default and Color3.fromRGB(0,200,255) or Color3.fromRGB(55,55,55)
    toggle.Text = ""
    toggle.BorderSizePixel = 0
    local on = default
    local indicator = Instance.new("Frame", toggle)
    indicator.Size = UDim2.new(0, 22, 0, 22)
    indicator.Position = UDim2.new(0, on and 22 or 2, 0, 3)
    indicator.BackgroundColor3 = on and Color3.fromRGB(0,200,255) or Color3.fromRGB(60,60,60)
    indicator.BorderSizePixel = 0
    toggle.MouseButton1Click:Connect(function()
        on = not on
        toggle.BackgroundColor3 = on and Color3.fromRGB(0,200,255) or Color3.fromRGB(55,55,55)
        indicator.Position = UDim2.new(0, on and 22 or 2, 0, 3)
        indicator.BackgroundColor3 = on and Color3.fromRGB(0,200,255) or Color3.fromRGB(60,60,60)
        if callback then callback(on) end
    end)
    if callback then callback(default) end
    return toggle
end

-- SLIDER
local function addSlider(parent, y, label, min, max, value, callback)
    local text = Instance.new("TextLabel", parent)
    text.Size = UDim2.new(0.6, 0, 0, 28)
    text.Position = UDim2.new(0, 30, 0, y)
    text.Text = label
    text.Font = Enum.Font.SourceSans
    text.TextSize = 19
    text.BackgroundTransparency = 1
    text.TextColor3 = Color3.new(1,1,1)

    local sliderBG = Instance.new("Frame", parent)
    sliderBG.Size = UDim2.new(0, 430, 0, 24)
    sliderBG.Position = UDim2.new(0, 30, 0, y+35)
    sliderBG.BackgroundColor3 = Color3.fromRGB(38,38,46)
    sliderBG.BorderSizePixel = 0

    local bar = Instance.new("Frame", sliderBG)
    bar.Size = UDim2.new((value-min)/(max-min), 0, 1, 0)
    bar.BackgroundColor3 = Color3.fromRGB(0,120,255)
    bar.BorderSizePixel = 0

    local valueBox = Instance.new("TextBox", parent)
    valueBox.Size = UDim2.new(0, 60, 0, 28)
    valueBox.Position = UDim2.new(0, 470, 0, y+31)
    valueBox.Text = tostring(value)
    valueBox.TextColor3 = Color3.new(1,1,1)
    valueBox.BackgroundColor3 = Color3.fromRGB(25,25,30)
    valueBox.Font = Enum.Font.SourceSansBold
    valueBox.TextSize = 18
    valueBox.ClearTextOnFocus = false

    local dragging = false
    local origDraggable = main.Draggable

    local function update(val)
        value = math.clamp(val, min, max)
        bar.Size = UDim2.new((value-min)/(max-min), 0, 1, 0)
        valueBox.Text = tostring(math.floor(value))
        if callback then callback(value) end
    end
    sliderBG.InputBegan:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 then
            dragging = true
            origDraggable = main.Draggable
            main.Draggable = false
            local con
            con = game:GetService("UserInputService").InputChanged:Connect(function(i)
                if i.UserInputType==Enum.UserInputType.MouseMovement and dragging then
                    local x = math.clamp((i.Position.X-sliderBG.AbsolutePosition.X)/sliderBG.AbsoluteSize.X, 0, 1)
                    update(math.floor(min + (max-min)*x))
                end
            end)
            game:GetService("UserInputService").InputEnded:Connect(function(i2)
                if i2.UserInputType==Enum.UserInputType.MouseButton1 then
                    dragging = false
                    main.Draggable = origDraggable
                    if con then con:Disconnect() end
                end
            end)
        end
    end)
    valueBox.FocusLost:Connect(function()
        local num = tonumber(valueBox.Text)
        if num then update(num) end
    end)
    update(value)
    return valueBox
end

----------------- MAIN TAB ------------------
addSwitch(tabFrames.Main, 0, "Ativar Aimbot", false, function(b) state.AimbotActive = b end)
addSwitch(tabFrames.Main, 40, "Team Check", false, function(b) state.TeamCheck = b end)
addSwitch(tabFrames.Main, 80, "Wall Check", false, function(b) state.WallCheck = b end)
addSlider(tabFrames.Main, 120, "Tamanho do FOV", fovMin, fovMax, 100, function(v) state.FOV = v end)

-- Toggle: Mouse2 or Key, funcionando corretamente
local holdLbl = Instance.new("TextLabel", tabFrames.Main)
holdLbl.Size = UDim2.new(0, 180, 0, 26)
holdLbl.Position = UDim2.new(0, 30, 0, 190)
holdLbl.Text = "Botao do aimbot:"
holdLbl.Font = Enum.Font.SourceSans
holdLbl.TextSize = 18
holdLbl.BackgroundTransparency = 1
holdLbl.TextColor3 = Color3.fromRGB(180,180,180)

local mouseBtn = Instance.new("TextButton", tabFrames.Main)
mouseBtn.Size = UDim2.new(0, 100, 0, 26)
mouseBtn.Position = UDim2.new(0, 200, 0, 190)
mouseBtn.Text = "Mouse2"
mouseBtn.BackgroundColor3 = Color3.fromRGB(0,200,255)
mouseBtn.TextColor3 = Color3.new(1,1,1)
mouseBtn.Font = Enum.Font.SourceSansBold
mouseBtn.TextSize = 18

local keyBtn = Instance.new("TextButton", tabFrames.Main)
keyBtn.Size = UDim2.new(0, 100, 0, 26)
keyBtn.Position = UDim2.new(0, 310, 0, 190)
keyBtn.Text = "Q"
keyBtn.BackgroundColor3 = Color3.fromRGB(55,55,55)
keyBtn.TextColor3 = Color3.new(1,1,1)
keyBtn.Font = Enum.Font.SourceSansBold
keyBtn.TextSize = 18

local keyOptions = {"Q","E","F","LeftAlt","LeftControl"}
local keyIndex = 1

local function updateHoldButtons()
    if state.HoldType == "Mouse2" then
        mouseBtn.BackgroundColor3 = Color3.fromRGB(0,200,255)
        keyBtn.BackgroundColor3 = Color3.fromRGB(55,55,55)
        keyBtn.Text = keyOptions[keyIndex]
    else
        mouseBtn.BackgroundColor3 = Color3.fromRGB(55,55,55)
        keyBtn.BackgroundColor3 = Color3.fromRGB(0,200,255)
        keyBtn.Text = keyOptions[keyIndex]
    end
end

mouseBtn.MouseButton1Click:Connect(function()
    state.HoldType = "Mouse2"
    updateHoldButtons()
end)
keyBtn.MouseButton1Click:Connect(function()
    state.HoldType = "Key"
    keyIndex = (keyIndex % #keyOptions) + 1
    state.HoldKey = Enum.KeyCode[keyOptions[keyIndex]]
    updateHoldButtons()
end)
updateHoldButtons()

----------------- ESP TAB ------------------
addSwitch(tabFrames.ESP, 0, "Ativar ESP (Highlight)", false, function(on) state.ESPActive = on end)
addSwitch(tabFrames.ESP, 40, "Team Check ESP", true, function(on) state.ESPTeamCheck = on end)
local espColorBtn = Instance.new("TextButton", tabFrames.ESP)
espColorBtn.Position = UDim2.new(0,30,0,85)
espColorBtn.Size = UDim2.new(0,150,0,28)
espColorBtn.Text = "Cor do Highlight"
espColorBtn.BackgroundColor3 = state.ESPColor
espColorBtn.TextColor3 = Color3.new(1,1,1)
espColorBtn.Font = Enum.Font.SourceSansBold
espColorBtn.TextSize = 18
espColorBtn.MouseButton1Click:Connect(function()
    local c = espColorBtn.BackgroundColor3
    local nextC = (c.r==1 and c.g==0 and c.b==0) and Color3.new(0,1,0) or (c.g==1 and c.r==0) and Color3.new(0,0,1) or Color3.new(1,0,0)
    espColorBtn.BackgroundColor3 = nextC
    state.ESPColor = nextC
end)

----------------- VISUAL TAB ------------------
addSwitch(tabFrames.Visual, 0, "FOV Arco-iris", false, function(on) state.RainbowFOV = on end)
local fovColorBtn = Instance.new("TextButton", tabFrames.Visual)
fovColorBtn.Position = UDim2.new(0,30,0,40)
fovColorBtn.Size = UDim2.new(0,150,0,28)
fovColorBtn.Text = "Cor do FOV"
fovColorBtn.BackgroundColor3 = state.FOVColor
fovColorBtn.TextColor3 = Color3.new(1,1,1)
fovColorBtn.Font = Enum.Font.SourceSansBold
fovColorBtn.TextSize = 18
fovColorBtn.MouseButton1Click:Connect(function()
    local c = fovColorBtn.BackgroundColor3
    local nextC = (c.r==0 and c.g==0.47 and c.b==1) and Color3.new(0,1,0) or (c.g==1 and c.r==0) and Color3.new(1,1,0) or Color3.new(0,0.47,1)
    fovColorBtn.BackgroundColor3 = nextC
    state.FOVColor = nextC
end)
addSwitch(tabFrames.Visual, 80, "Slow Motion PvP", false, function(on) state.SlowMotion = on end)
addSwitch(tabFrames.Visual, 120, "Ceu PvP Suave", false, function(on) state.SmoothSky = on end)

----------------- OTIMIZACAO TAB ------------------
local fpsBtn = Instance.new("TextButton", tabFrames.Otimizacao)
fpsBtn.Position = UDim2.new(0,30,0,0)
fpsBtn.Size = UDim2.new(0,240,0,32)
fpsBtn.Text = "Otimizar FPS"
fpsBtn.BackgroundColor3 = Color3.fromRGB(38,38,46)
fpsBtn.TextColor3 = Color3.new(1,1,1)
fpsBtn.Font = Enum.Font.SourceSans
fpsBtn.TextSize = 17
fpsBtn.MouseButton1Click:Connect(function()
    settings().Rendering.QualityLevel = Enum.QualityLevel.Level01
    settings().Rendering.MeshPartDetailLevel = Enum.MeshPartDetailLevel.Low
    Lighting.GlobalShadows = false
end)

local fpsUnlock = Instance.new("TextButton", tabFrames.Otimizacao)
fpsUnlock.Position = UDim2.new(0,30,0,40)
fpsUnlock.Size = UDim2.new(0,240,0,32)
fpsUnlock.Text = "FPS Unlocker (sem limite 60 FPS)"
fpsUnlock.BackgroundColor3 = Color3.fromRGB(38,38,46)
fpsUnlock.TextColor3 = Color3.new(1,1,1)
fpsUnlock.Font = Enum.Font.SourceSans
fpsUnlock.TextSize = 17
fpsUnlock.MouseButton1Click:Connect(function()
    state.FPSUnlock = not state.FPSUnlock
    if setfpscap then
        if state.FPSUnlock then setfpscap(999) else setfpscap(60) end
    end
    fpsUnlock.Text = state.FPSUnlock and "FPS Unlocker [ON]" or "FPS Unlocker (sem limite 60 FPS)"
end)

local pingBtn = Instance.new("TextButton", tabFrames.Otimizacao)
pingBtn.Position = UDim2.new(0,30,0,80)
pingBtn.Size = UDim2.new(0,240,0,32)
pingBtn.Text = "Otimizar Ping"
pingBtn.BackgroundColor3 = Color3.fromRGB(38,38,46)
pingBtn.TextColor3 = Color3.new(1,1,1)
pingBtn.Font = Enum.Font.SourceSans
pingBtn.TextSize = 17
pingBtn.MouseButton1Click:Connect(function()
    game:GetService("NetworkSettings").IncomingReplicationLag = 0.1
end)

local skyboxBtn = Instance.new("TextButton", tabFrames.Otimizacao)
skyboxBtn.Position = UDim2.new(0,30,0,120)
skyboxBtn.Size = UDim2.new(0,240,0,32)
skyboxBtn.Text = "Skybox PvP (claro)"
skyboxBtn.BackgroundColor3 = Color3.fromRGB(38,38,46)
skyboxBtn.TextColor3 = Color3.new(1,1,1)
skyboxBtn.Font = Enum.Font.SourceSans
skyboxBtn.TextSize = 17
skyboxBtn.MouseButton1Click:Connect(function()
    for _,v in ipairs(Lighting:GetChildren()) do
        if v:IsA("Sky") then v:Destroy() end
    end
    local sky = Instance.new("Sky",Lighting)
    sky.SkyboxBk = "http://www.roblox.com/asset/?id=159454299"
    sky.SkyboxDn = "http://www.roblox.com/asset/?id=159454296"
    sky.SkyboxFt = "http://www.roblox.com/asset/?id=159454293"
    sky.SkyboxLf = "http://www.roblox.com/asset/?id=159454286"
    sky.SkyboxRt = "http://www.roblox.com/asset/?id=159454300"
    sky.SkyboxUp = "http://www.roblox.com/asset/?id=159454288"
end)

----------------- CREDITOS TAB ------------------
local creditsTxt = Instance.new("TextLabel", tabFrames.Creditos)
creditsTxt.Size = UDim2.new(1, -40, 1, -40)
creditsTxt.Position = UDim2.new(0, 20, 0, 20)
creditsTxt.BackgroundTransparency = 1
creditsTxt.Text = "Quer um script desse totalmente exclusivo para voce?\nMe chama no discord: vitinxzsw."
creditsTxt.TextColor3 = Color3.fromRGB(200,200,255)
creditsTxt.Font = Enum.Font.SourceSansBold
creditsTxt.TextSize = 24
creditsTxt.TextWrapped = true

---------------------- FOV CIRCLE CENTER SCREEN ----------------------
local fovCircle = Drawing and Drawing.new("Circle") or nil
if fovCircle then
    fovCircle.Thickness = 2
    fovCircle.Filled = false
    fovCircle.Visible = true
end

-- Funcao de wallcheck robusta (compatível com qualquer executor)
local function isVisible(fromPos, toPos)
    local cam = workspace.CurrentCamera
    if cam and cam.GetPartsObscuringTarget then
        local parts = cam:GetPartsObscuringTarget({fromPos}, toPos)
        return #parts == 0
    end
    return true
end

-- getClosest atualizado com TeamCheck universal
local function getClosest()
    local cam = workspace.CurrentCamera
    local cx, cy = cam.ViewportSize.X/2, cam.ViewportSize.Y/2
    local closest, dist = nil, math.huge
    for _,p in ipairs(Players:GetPlayers()) do
        if p ~= LP and p.Character and p.Character:FindFirstChild("Head") and p.Character:FindFirstChild("Humanoid") and p.Character.Humanoid.Health>0 then
            local isEnemy = true
            if state.TeamCheck then
                if LP.Team ~= nil and p.Team ~= nil then
                    isEnemy = (LP.Team ~= p.Team)
                elseif LP.TeamColor ~= nil and p.TeamColor ~= nil then
                    isEnemy = (LP.TeamColor ~= p.TeamColor)
                end
            end
            if isEnemy then
                local visible = true
                if state.WallCheck then
                    visible = isVisible(cam.CFrame.Position, p.Character.Head.Position)
                end
                if visible then
                    local pos, onscreen = cam:WorldToViewportPoint(p.Character.Head.Position)
                    local d = (Vector2.new(pos.X, pos.Y) - Vector2.new(cx, cy)).Magnitude
                    if d < dist and d < state.FOV then
                        dist = d
                        closest = p
                    end
                end
            end
        end
    end
    return closest
end

---------------------- AIMBOT & ESP FUNCTIONAL ----------------------
local isAimbotHeld = false
UIS.InputBegan:Connect(function(input,gp)
    if gp then return end
    if state.HoldType == "Key" and input.KeyCode == state.HoldKey then
        isAimbotHeld = true
    end
    if state.HoldType == "Mouse2" and input.UserInputType == Enum.UserInputType.MouseButton2 then
        isAimbotHeld = true
    end
end)
UIS.InputEnded:Connect(function(input,gp)
    if gp then return end
    if state.HoldType == "Key" and input.KeyCode == state.HoldKey then
        isAimbotHeld = false
    end
    if state.HoldType == "Mouse2" and input.UserInputType == Enum.UserInputType.MouseButton2 then
        isAimbotHeld = false
    end
end)

RunService.RenderStepped:Connect(function()
    -- FOV circle
    if main.Visible and fovCircle then
        local cam = workspace.CurrentCamera
        fovCircle.Position = Vector2.new(cam.ViewportSize.X/2, cam.ViewportSize.Y/2)
        fovCircle.Radius = state.FOV
        if state.RainbowFOV then
            fovCircle.Color = Color3.fromHSV((tick()%5)/5,1,1)
        else
            fovCircle.Color = state.FOVColor
        end
        fovCircle.Visible = tabFrames["Main"].Visible or tabFrames["Visual"].Visible
    end
    -- Aimbot (agora funciona com arma na mao, mira em Head ou em HumanoidRootPart se nao tiver Head)
    if state.AimbotActive and isAimbotHeld then
        local target = getClosest()
        if target and target.Character then
            local aimPart = target.Character:FindFirstChild("Head") or target.Character:FindFirstChild("HumanoidRootPart")
            if aimPart then
                workspace.CurrentCamera.CFrame = CFrame.new(workspace.CurrentCamera.CFrame.Position, aimPart.Position)
            end
        end
    end
    -- ESP Highlight
    for _,p in ipairs(Players:GetPlayers()) do
        if p ~= LP and p.Character and p.Character:FindFirstChild("HumanoidRootPart") then
            local isEnemy = true
            if state.ESPTeamCheck then
                if LP.Team ~= nil and p.Team ~= nil then
                    isEnemy = (LP.Team ~= p.Team)
                elseif LP.TeamColor ~= nil and p.TeamColor ~= nil then
                    isEnemy = (LP.TeamColor ~= p.TeamColor)
                end
            end
            if state.ESPActive and isEnemy then
                if not p.Character:FindFirstChild("AIMFOV_HL") then
                    local hl = Instance.new("Highlight")
                    hl.Name = "AIMFOV_HL"
                    hl.FillColor = state.ESPColor
                    hl.OutlineColor = Color3.new(1,1,1)
                    hl.Adornee = p.Character
                    hl.Parent = p.Character
                else
                    p.Character.AIMFOV_HL.FillColor = state.ESPColor
                end
            else
                if p.Character:FindFirstChild("AIMFOV_HL") then
                    p.Character.AIMFOV_HL:Destroy()
                end
            end
        end
    end
    -- Slow Motion PvP
    if state.SlowMotion then
        workspace.Gravity = 100
        Lighting.ClockTime = 2
    else
        workspace.Gravity = 196.2
    end
    -- Ceu PvP Suave
    if state.SmoothSky then
        Lighting.Ambient = Color3.new(0.7,0.7,0.9)
    else
        Lighting.Ambient = Color3.new(0.5,0.5,0.5)
    end
end)
