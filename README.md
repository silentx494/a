-- Gui to Lua
-- Version: 3.2

-- Instances:

local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local gamepass = Instance.new("TextButton")
local close = Instance.new("TextButton")
local label = Instance.new("TextLabel")

--Properties:

ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(99, 255, 255)
Frame.BorderSizePixel = 0
Frame.Position = UDim2.new(0.0828025341, 0, 0.113144755, 0)
Frame.Size = UDim2.new(0, 312, 0, 284)

gamepass.Name = "gamepass"
gamepass.Parent = Frame
gamepass.BackgroundColor3 = Color3.fromRGB(42, 255, 56)
gamepass.BorderSizePixel = 0
gamepass.Position = UDim2.new(0.224987447, 0, 0.387323946, 0)
gamepass.Size = UDim2.new(0, 142, 0, 50)
gamepass.Font = Enum.Font.SourceSans
gamepass.Text = "Free GamePass"
gamepass.TextColor3 = Color3.fromRGB(255, 255, 255)
gamepass.TextScaled = true
gamepass.TextSize = 14.000
gamepass.TextWrapped = true

close.Name = "close"
close.Parent = Frame
close.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
close.BackgroundTransparency = 1.000
close.BorderSizePixel = 0
close.Position = UDim2.new(0.906611443, 0, 0, 0)
close.Size = UDim2.new(0, 29, 0, 38)
close.Font = Enum.Font.SourceSans
close.Text = "X"
close.TextColor3 = Color3.fromRGB(255, 0, 0)
close.TextScaled = true
close.TextSize = 14.000
close.TextWrapped = true

label.Name = "label"
label.Parent = Frame
label.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
label.BackgroundTransparency = 1.000
label.BorderSizePixel = 0
label.Position = UDim2.new(0.131913155, 0, 0, 0)
label.Size = UDim2.new(0, 201, 0, 74)
label.Font = Enum.Font.SourceSans
label.Text = "Cabin Gui"
label.TextColor3 = Color3.fromRGB(255, 255, 255)
label.TextScaled = true
label.TextSize = 14.000
label.TextWrapped = true

-- Scripts:

local function SXCLF_fake_script() -- gamepass.LocalScript 
	local script = Instance.new('LocalScript', gamepass)

	click = script.Parent
	
	click.MouseButton1Click:Connect(function()
		game:GetService("Players").LocalPlayer.gamepasses["premium_room"].Value = true
		wait()
		game:GetService("Players").LocalPlayer.gamepasses["custom_music"].Value = true
		wait()
		game:GetService("Players").LocalPlayer.gamepasses["emergency_control"].Value = true
		wait()
		game:GetService("Players").LocalPlayer.gamepasses["custom_lighting"].Value = true
		wait()
		game:GetService("Players").LocalPlayer.gamepasses["extra_design"].Value = true
		wait()
		game:GetService("Players").LocalPlayer.gamepasses["multiplayer"].Value = true
		wait()
		game:GetService("Players").LocalPlayer.gamepasses["premium_flight_attendant"].Value = true
		wait()
		game:GetService("Players").LocalPlayer.gamepasses["tail_logo"].Value = true
		wait()
		game:GetService("Players").LocalPlayer.gamepasses["x2_earnings"].Value = true
		wait()
		game:GetService("Players").LocalPlayer.gamepasses["vip"].Value = true
	end)
end
coroutine.wrap(SXCLF_fake_script)()
local function QZVE_fake_script() -- close.LocalScript 
	local script = Instance.new('LocalScript', close)

	close = script.Parent
	gui = script.Parent.Parent
	
	close.MouseButton1Click:Connect(function()
		gui:Destroy()
	end)
	
end
coroutine.wrap(QZVE_fake_script)()
local function TFXUC_fake_script() -- Frame.LocalScript 
	local script = Instance.new('LocalScript', Frame)

	local UserInputService = game:GetService("UserInputService")
	
	local MainFrame = script.Parent
	local TopBar = MainFrame:WaitForChild("label")
	
	local Camera = workspace:WaitForChild("Camera")
	
	local DragMousePosition
	local FramePosition
	
	local Draggable = false
	
	TopBar.InputBegan:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
			Draggable = true
			DragMousePosition = Vector2.new(input.Position.x, input.Position.Y)
			FramePosition = Vector2.new(MainFrame.Position.X.Scale, MainFrame.Position.Y.Scale)
		end
	end)
	
	TopBar.InputEnded:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
			Draggable = false
		end
	end)
	
	UserInputService.InputChanged:Connect(function(input)
		if Draggable == true then
			local NewPosition = FramePosition + ((Vector2.new(input.Position.X, input.Position.Y) - DragMousePosition) / Camera.ViewportSize)
			MainFrame.Position = UDim2.new(NewPosition.X, 0, NewPosition.Y, 0)
		end
	end)
end
coroutine.wrap(TFXUC_fake_script)()
