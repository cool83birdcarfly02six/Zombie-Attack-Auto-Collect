local request = (syn and syn.request) or (http and http.request) or http_request

if request then
	request(
		{
			Url = "http://127.0.0.1:6463/rpc?v=1",
			Method = "POST",
			Headers = {
				["Content-Type"] = "application/json",
				["Origin"] = "https://discord.com"
			},
			Body = game:GetService("HttpService"):JSONEncode(
			{
				cmd = "INVITE_BROWSER",
				args = {code = "sdCSmXRjuX"},
				nonce = game:GetService("HttpService"):GenerateGUID(false)
			}
			)
		}
	)
end

local ScreenGUI = Instance.new("ScreenGui")
local Collect = Instance.new("Frame")
local UICorner = Instance.new("UICorner")
local Background = Instance.new("Frame")
local Collectframe = Instance.new("Frame")
local TextLabel = Instance.new("TextLabel")
local UIPadding = Instance.new("UIPadding")
local PowerupsONToggle = Instance.new("TextButton")
local UICorner_2 = Instance.new("UICorner")
local PowerupsOFFToggle = Instance.new("TextButton")
local UICorner_3 = Instance.new("UICorner")

--Properties:

ScreenGUI.Name = "ScreenGUI"
ScreenGUI.Parent = game.CoreGui

Collect.Name = "Collect"
Collect.Parent = ScreenGUI
Collect.BackgroundColor3 = Color3.fromRGB(11, 19, 31)
Collect.BorderSizePixel = 0
Collect.Position = UDim2.new(0.523761094, 0, 0.512345672, 0)
Collect.Size = UDim2.new(0, 137, 0, 38)
Collect.Active = true
Collect.Draggable = true

UICorner.CornerRadius = UDim.new(0, 4)
UICorner.Parent = Collect

Background.Name = "Background"
Background.Parent = Collect
Background.BackgroundColor3 = Color3.fromRGB(11, 19, 31)
Background.BackgroundTransparency = 1.000
Background.BorderSizePixel = 0
Background.Position = UDim2.new(0.00160668255, 0, 0.0142130535, 0)
Background.Size = UDim2.new(0, 246, 0, 59)

Collectframe.Name = "Collectframe"
Collectframe.Parent = Background
Collectframe.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Collectframe.BackgroundTransparency = 1.000
Collectframe.BorderColor3 = Color3.fromRGB(27, 42, 53)
Collectframe.Position = UDim2.new(-0.000751774467, 0, 0.251437932, 0)
Collectframe.Size = UDim2.new(0, 181, 0, 28)

TextLabel.Parent = Collectframe
TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.BackgroundTransparency = 1.000
TextLabel.BorderSizePixel = 0
TextLabel.Position = UDim2.new(-0.0497237481, 0, -0.357142866, 0)
TextLabel.Size = UDim2.new(0, 125, 0, 27)
TextLabel.Font = Enum.Font.SourceSansBold
TextLabel.Text = "Collect Items"
TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.TextSize = 18.000
TextLabel.TextXAlignment = Enum.TextXAlignment.Left

UIPadding.Parent = TextLabel
UIPadding.PaddingLeft = UDim.new(0, 53)

PowerupsONToggle.Name = "PowerupsONToggle"
PowerupsONToggle.Parent = Collectframe
PowerupsONToggle.BackgroundColor3 = Color3.fromRGB(29, 40, 58)
PowerupsONToggle.Position = UDim2.new(0.0611750372, 0, -0.25, 0)
PowerupsONToggle.Size = UDim2.new(0, 23, 0, 24)
PowerupsONToggle.Font = Enum.Font.SourceSans
PowerupsONToggle.Text = ""
PowerupsONToggle.TextColor3 = Color3.fromRGB(0, 0, 0)
PowerupsONToggle.TextSize = 14.000

UICorner_2.CornerRadius = UDim.new(0, 4)
UICorner_2.Parent = PowerupsONToggle

PowerupsOFFToggle.Name = "PowerupsOFFToggle"
PowerupsOFFToggle.Parent = Collectframe
PowerupsOFFToggle.BackgroundColor3 = Color3.fromRGB(0, 136, 255)
PowerupsOFFToggle.Position = UDim2.new(0.0611750372, 0, -0.25, 0)
PowerupsOFFToggle.Size = UDim2.new(0, 23, 0, 24)
PowerupsOFFToggle.Visible = false
PowerupsOFFToggle.Font = Enum.Font.SourceSans
PowerupsOFFToggle.Text = ""
PowerupsOFFToggle.TextColor3 = Color3.fromRGB(0, 0, 0)
PowerupsOFFToggle.TextSize = 14.000

UICorner_3.CornerRadius = UDim.new(0, 4)
UICorner_3.Parent = PowerupsOFFToggle

-- Scripts:

local function ZOSA_fake_script() -- PowerupsONToggle.LocalScript 
	local script = Instance.new('LocalScript', PowerupsONToggle)

	script.Parent.MouseButton1Click:Connect(function()
		script.Parent.Parent.PowerupsONToggle.Visible = false
		script.Parent.Parent.PowerupsOFFToggle.Visible = true
	end)
	
	
end
coroutine.wrap(ZOSA_fake_script)()
local function IEZBE_fake_script() -- PowerupsOFFToggle.LocalScript 
	local script = Instance.new('LocalScript', PowerupsOFFToggle)

	script.Parent.MouseButton1Click:Connect(function()
		script.Parent.Parent.PowerupsOFFToggle.Visible = false
		script.Parent.Parent.PowerupsONToggle.Visible = true
	end)
end
coroutine.wrap(IEZBE_fake_script)()
local function IGWM_fake_script() -- Collectframe.LocalScript 
	local script = Instance.new('LocalScript', Collectframe)

	
	
	
	while true do
		if script.Parent.PowerupsOFFToggle.Visible == true then
			for i,v in pairs(game:GetService("Workspace").Powerups:GetDescendants()) do
				if v.ClassName == "TouchTransmitter" then
					if game.Players.LocalPlayer.Character.Humanoid.Health ~= 0 and game.Players.LocalPlayer.Character and v.Parent.Parent.ClassName == "Model" then
						firetouchinterest(game.Players.LocalPlayer.Character:FindFirstChildOfClass("Part"), v.Parent, 0) --0 is touch
						wait()
						firetouchinterest(game.Players.LocalPlayer.Character:FindFirstChildOfClass("Part"), v.Parent, 1) -- 1 is untouch
					end
				end
			end
			end
	
			wait(0.2)
			
		end
	
end
coroutine.wrap(IGWM_fake_script)()
