local player = game.Players.LocalPlayer
local ReplicatedStorage = game:GetService("ReplicatedStorage")

-- TELA DE SENHA

local gui = script.Parent

local PasswordFrame = Instance.new("Frame")
PasswordFrame.Size = UDim2.new(0,300,0,150)
PasswordFrame.Position = UDim2.new(0.5,-150,0.5,-75)
PasswordFrame.Parent = gui

local PasswordBox = Instance.new("TextBox")
PasswordBox.Size = UDim2.new(0,200,0,40)
PasswordBox.Position = UDim2.new(0.5,-100,0.3,0)
PasswordBox.PlaceholderText = "Digite a senha"
PasswordBox.Parent = PasswordFrame

local EnterButton = Instance.new("TextButton")
EnterButton.Size = UDim2.new(0,120,0,40)
EnterButton.Position = UDim2.new(0.5,-60,0.7,0)
EnterButton.Text = "Entrar"
EnterButton.Parent = PasswordFrame

-- BOTÃO FLUTUANTE

local FloatButton = Instance.new("TextButton")
FloatButton.Size = UDim2.new(0,70,0,70)
FloatButton.Position = UDim2.new(0,20,0.5,-35)
FloatButton.Text = "🤙"
FloatButton.Visible = false
FloatButton.Parent = gui

-- MENU

local MenuFrame = Instance.new("Frame")
MenuFrame.Size = UDim2.new(0,250,0,200)
MenuFrame.Position = UDim2.new(0.5,-125,0.5,-100)
MenuFrame.Visible = false
MenuFrame.Parent = gui

local LocustButton = Instance.new("TextButton")
LocustButton.Size = UDim2.new(0,200,0,50)
LocustButton.Position = UDim2.new(0.5,-100,0,20)
LocustButton.Text = "THE LOCUST MORPH"
LocustButton.Parent = MenuFrame

local SonicButton = Instance.new("TextButton")
SonicButton.Size = UDim2.new(0,200,0,50)
SonicButton.Position = UDim2.new(0.5,-100,0,100)
SonicButton.Text = "SONIC MORPH"
SonicButton.Parent = MenuFrame

EnterButton.MouseButton1Click:Connect(function()
	if PasswordBox.Text == "2009" then
		PasswordFrame.Visible = false
		FloatButton.Visible = true
	end
end)

FloatButton.MouseButton1Click:Connect(function()
	MenuFrame.Visible = not MenuFrame.Visible
end)

LocustButton.MouseButton1Click:Connect(function()
	ReplicatedStorage.MorphEvent:FireServer("Locust")
end)

SonicButton.MouseButton1Click:Connect(function()
	ReplicatedStorage.MorphEvent:FireServer("Sonic")
end)
