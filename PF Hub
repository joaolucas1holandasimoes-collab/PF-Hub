-- PF HUB (HALF SIZE VERSION)

local Players = game:GetService("Players")
local TextChatService = game:GetService("TextChatService")

local player = Players.LocalPlayer or Players.PlayerAdded:Wait()
local PlayerGui = player:WaitForChild("PlayerGui")

----------------------------------------------------
-- CHAT SYSTEM
----------------------------------------------------
local function sendMessage(msg)
    if TextChatService.ChatVersion == Enum.ChatVersion.TextChatService then
        local channel = TextChatService.TextChannels:FindFirstChild("RBXGeneral")
        if channel then
            channel:SendAsync(msg)
        end
    else
        player:Chat(msg)
    end
end

----------------------------------------------------
-- REMOVE ANTIGO
----------------------------------------------------
pcall(function()
    PlayerGui:FindFirstChild("PF_Hub"):Destroy()
end)

----------------------------------------------------
-- GUI BASE
----------------------------------------------------
local gui = Instance.new("ScreenGui")
gui.Name = "PF_Hub"
gui.Parent = PlayerGui
gui.ResetOnSpawn = false
gui.IgnoreGuiInset = true

-- Toggle (÷2)
local toggle = Instance.new("TextButton", gui)
toggle.Size = UDim2.new(0, 22, 0, 22)
toggle.Position = UDim2.new(0, 10, 0.5, 0)
toggle.Text = "PF"
toggle.BackgroundColor3 = Color3.fromRGB(150,0,0)
toggle.TextColor3 = Color3.new(1,1,1)
toggle.TextScaled = true
toggle.Draggable = true

----------------------------------------------------
-- PANEL (÷2)
----------------------------------------------------
local panel = Instance.new("Frame", gui)
panel.Size = UDim2.new(0, 155, 0, 110)
panel.Position = UDim2.new(0.5, -77, 0.5, -55)
panel.BackgroundColor3 = Color3.fromRGB(10,10,10)
panel.Visible = false
panel.Active = true
panel.Draggable = true

local stroke = Instance.new("UIStroke", panel)
stroke.Color = Color3.fromRGB(200,0,0)
stroke.Thickness = 1

-- Título (reduzido)
local title = Instance.new("TextLabel", panel)
title.Size = UDim2.new(1, 0, 0, 18)
title.BackgroundTransparency = 1
title.Text = "PF HUB"
title.TextColor3 = Color3.fromRGB(220,0,0)
title.Font = Enum.Font.GothamBold
title.TextScaled = true

----------------------------------------------------
-- BOTÃO PROPORCIONAL (÷2)
----------------------------------------------------
local function createButton(text, command, x, y)
    local btn = Instance.new("TextButton", panel)
    btn.Size = UDim2.new(0, 42, 0, 22)
    btn.Position = UDim2.new(x, 0, y, 0)
    btn.BackgroundColor3 = Color3.fromRGB(170,0,0)
    btn.TextColor3 = Color3.new(1,1,1)
    btn.Font = Enum.Font.GothamBold
    btn.TextScaled = true
    btn.Text = text

    btn.MouseButton1Click:Connect(function()
        sendMessage(command)
    end)
end

----------------------------------------------------
-- POSICIONAMENTO 3x2 (AJUSTADO)
----------------------------------------------------

-- Linha 1
createButton("FP", "/Furar Pneu", 0.05, 0.25)
createButton("MT", "/Mat",         0.37, 0.25)
createButton("RD", "/Render",      0.69, 0.25)

-- Linha 2
createButton("EV", "Encoste o veículo imediatamente.", 0.05, 0.55)
createButton("AG", "/Algemar",                          0.37, 0.55)
createButton("RV", "/Revistar",                         0.69, 0.55)

----------------------------------------------------
-- TOGGLE
----------------------------------------------------
toggle.MouseButton1Click:Connect(function()
    panel.Visible = not panel.Visible
end)

print("PF HUB HALF SIZE LOADED")
