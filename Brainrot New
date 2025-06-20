local player = game.Players.LocalPlayer
local gui = Instance.new("ScreenGui", player:WaitForChild("PlayerGui"))
gui.Name = "FaDhenModernMini"
gui.ResetOnSpawn = false

-- FRAME UTAMA (Kecil)
local mainFrame = Instance.new("Frame")
mainFrame.Size = UDim2.new(0, 220, 0, 230)
mainFrame.Position = UDim2.new(0.5, -110, 0.5, -130)
mainFrame.BackgroundColor3 = Color3.fromRGB(33, 33, 33)
mainFrame.Parent = gui
mainFrame.Active = true
mainFrame.Draggable = true
mainFrame.Visible = false

-- Tambahkan UICorner
Instance.new("UICorner", mainFrame).CornerRadius = UDim.new(0, 10)

-- Tambahkan UIStroke
local stroke = Instance.new("UIStroke", mainFrame)
stroke.Thickness = 2
stroke.Color = Color3.fromRGB(100, 100, 100)
stroke.Transparency = 0

-- SHADOW
local shadow = Instance.new("ImageLabel", mainFrame)
shadow.AnchorPoint = Vector2.new(0.5, 0.5)
shadow.Position = UDim2.new(0.5, 0, 0.5, 0)
shadow.Size = UDim2.new(1, 20, 1, 20)
shadow.Image = "rbxassetid://5028857084"
shadow.ImageColor3 = Color3.new(0, 0, 0)
shadow.ImageTransparency = 0.7
shadow.ScaleType = Enum.ScaleType.Slice
shadow.SliceCenter = Rect.new(24, 24, 276, 276)
shadow.BackgroundTransparency = 1
shadow.ZIndex = 0

-- JUDUL
local title = Instance.new("TextLabel", mainFrame)
title.Size = UDim2.new(1, 0, 0, 28)
title.BackgroundTransparency = 1
title.Text = "XxLegendxX"
title.Font = Enum.Font.GothamBold
title.TextSize = 13
title.TextColor3 = Color3.fromRGB(255, 255, 255)

-- TAB CONTAINER
local tabContainer = Instance.new("Frame", mainFrame)
tabContainer.Size = UDim2.new(1, -16, 0, 24)
tabContainer.Position = UDim2.new(0, 8, 0, 30)
tabContainer.BackgroundTransparency = 1

local tabLayout = Instance.new("UIListLayout", tabContainer)
tabLayout.FillDirection = Enum.FillDirection.Horizontal
tabLayout.Padding = UDim.new(0, 5)
tabLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center

-- ISI KONTEN
local contentFrame = Instance.new("Frame", mainFrame)
contentFrame.Position = UDim2.new(0, 8, 0, 60)
contentFrame.Size = UDim2.new(1, -16, 1, -70)
contentFrame.BackgroundTransparency = 1

-- TAB
local tabs = {}
local function createTab(name)
	local tab = Instance.new("Frame", contentFrame)
	tab.Size = UDim2.new(1, 0, 1, 0)
	tab.BackgroundTransparency = 1
	tab.Visible = false

	local layout = Instance.new("UIListLayout", tab)
	layout.Padding = UDim.new(0, 6)
	layout.VerticalAlignment = Enum.VerticalAlignment.Top
	layout.HorizontalAlignment = Enum.HorizontalAlignment.Center

	tabs[name] = tab
	return tab
end

local mainTab = createTab("Main")
local visualTab = createTab("Visual")
local miscTab = createTab("Misc")

local function switchTab(name)
	for tabName, tab in pairs(tabs) do
		tab.Visible = (tabName == name)
	end
end

-- TOMBOL TAB MINI
local function createTabButton(text, tabName)
	local btn = Instance.new("TextButton", tabContainer)
	btn.Size = UDim2.new(0, 60, 0, 22)
	btn.Text = text
	btn.Font = Enum.Font.Gotham
	btn.TextSize = 13
	btn.TextColor3 = Color3.fromRGB(255, 255, 255)
	btn.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
	Instance.new("UICorner", btn).CornerRadius = UDim.new(0, 6)

	btn.MouseButton1Click:Connect(function()
		switchTab(tabName)
	end)
end

createTabButton("Main", "Main")
createTabButton("Visual", "Visual")
createTabButton("Misc", "Misc")

-- TOGGLE MINI (TANPA ICON)
local function AddToggle(tab, data)
	local btn = Instance.new("TextButton", tab)
	btn.Size = UDim2.new(1, -10, 0, 28)
	btn.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
	btn.TextColor3 = Color3.fromRGB(230, 230, 230)
	btn.Font = Enum.Font.Gotham
	btn.TextSize = 15
	btn.TextXAlignment = Enum.TextXAlignment.Left
	btn.Text = data.Name -- Tidak ada icon
	btn.AutoButtonColor = false
	Instance.new("UICorner", btn).CornerRadius = UDim.new(0, 8)

	local toggle = Instance.new("Frame", btn)
	toggle.Size = UDim2.new(0, 12, 0, 12)
	toggle.Position = UDim2.new(1, -20, 0.5, -6)
	toggle.BackgroundColor3 = Color3.fromRGB(130, 130, 130)
	toggle.BorderSizePixel = 0
	Instance.new("UICorner", toggle).CornerRadius = UDim.new(1, 0)

	local state = false
	btn.MouseButton1Click:Connect(function()
		state = not state
		toggle.BackgroundColor3 = state and Color3.fromRGB(0, 200, 100) or Color3.fromRGB(130, 130, 130)
		if data.Callback then
			data.Callback(state)
		end
	end)
end



-- TOGGLE AUTO STEAL
AddToggle(mainTab, {
	Name = "auto Steal",
	Callback = function(v)
		print("Godmode:", v)
		if v then
			-- Saat toggle diaktifkan (ON)
			loadstring(game:HttpGet("https://raw.githubusercontent.com/Youifpg/Steal-a-Brianrot/refs/heads/main/Instant%20steal.lua"))()
		end
	end
})




AddToggle(mainTab, {
	Name = "TP Shop",
	Callback = function(v)
		if v then
			local player = game.Players.LocalPlayer
			local character = player.Character or player.CharacterAdded:Wait()
			local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

			local cf = CFrame.new(
				-378.420959, -6.25197887, 59.4905052,
				0.106838159, -1.85177775e-08, 0.994276404,
				1.08971683e-07, 1, 6.91502233e-09,
				-0.994276404, 1.07609189e-07, 0.106838159
			)

			humanoidRootPart.CFrame = cf
			humanoidRootPart.Anchored = true
			print("✅ Teleport ke Shop dan Anchor aktif 2 detik.")

			task.delay(2, function()
				humanoidRootPart.Anchored = false
				print("🔓 Anchor dilepas.")
			end)
		end
	end
})



local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local player = Players.LocalPlayer

-- Variabel global
local boostGui
local enforceConnection
local boostBtn
local boostAktif = false

-- Fungsi aktifkan speed
local function startEnforceSpeed()
	local character = player.Character or player.CharacterAdded:Wait()
	local humanoid = character:WaitForChild("Humanoid")

	enforceConnection = RunService.Heartbeat:Connect(function()
		if humanoid.WalkSpeed ~= 42 then
			humanoid.WalkSpeed = 42
		end
	end)

	humanoid:GetPropertyChangedSignal("WalkSpeed"):Connect(function()
		if boostAktif and humanoid.WalkSpeed ~= 42 then
			humanoid.WalkSpeed = 42
		end
	end)
end

-- Fungsi matikan speed
local function stopEnforceSpeed()
	if enforceConnection then
		enforceConnection:Disconnect()
		enforceConnection = nil
	end

	local char = player.Character
	if char then
		local hum = char:FindFirstChildOfClass("Humanoid")
		if hum then
			hum.WalkSpeed = 16
		end
	end
end

-- Buat GUI Boost
local function buatBoostGUI()
	boostGui = Instance.new("ScreenGui", player:WaitForChild("PlayerGui"))
	boostGui.Name = "BoostGUI"
	boostGui.ResetOnSpawn = false

	boostBtn = Instance.new("TextButton", boostGui)
	boostBtn.Size = UDim2.new(0, 120, 0, 40)
	boostBtn.Position = UDim2.new(0.5, 0, 1, -70) -- ✅ TEPAT DI TENGAH BAWAH
	boostBtn.AnchorPoint = Vector2.new(0.5, 1) -- ✅ Titik tengah bawah
	boostBtn.BackgroundColor3 = Color3.fromRGB(44, 44, 44)
	boostBtn.TextColor3 = Color3.new(1, 1, 1)
	boostBtn.Font = Enum.Font.GothamBold
	boostBtn.TextSize = 16
	boostBtn.BorderSizePixel = 0
	boostBtn.AutoButtonColor = false
	boostBtn.Text = "Boost OFF"

	-- UICorner
	local corner = Instance.new("UICorner")
	corner.CornerRadius = UDim.new(0, 10)
	corner.Parent = boostBtn

	-- UIStroke
	local stroke = Instance.new("UIStroke")
	stroke.Color = Color3.fromRGB(255, 255, 255)
	stroke.Thickness = 2
	stroke.Transparency = 0.3
	stroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	stroke.Parent = boostBtn

	-- ON/OFF logic
	boostBtn.MouseButton1Click:Connect(function()
		boostAktif = not boostAktif

		if boostAktif then
			boostBtn.Text = "Boost ON"
			startEnforceSpeed()
		else
			boostBtn.Text = "Boost OFF"
			stopEnforceSpeed()
		end
	end)
end

-- Hapus GUI
local function hapusBoostGUI()
	if boostGui then
		boostGui:Destroy()
		boostGui = nil
	end
	stopEnforceSpeed()
	boostAktif = false
end

-- Toggle GUI
AddToggle(mainTab, {
	Name = "Boost Speed",
	Callback = function(v)
		if v then
			buatBoostGUI()
		else
			hapusBoostGUI()
		end
	end
})






AddToggle(mainTab, {
	Name = "Reset",
	Callback = function(v)
		print("Godmode:", v)
		if v then
			local player = game.Players.LocalPlayer
			local character = player.Character or player.CharacterAdded:Wait()

			-- Kurangi darah menjadi 0 untuk reset karakter
			local humanoid = character:FindFirstChildOfClass("Humanoid")
			if humanoid then
				humanoid.Health = 0
			end
		end
	end
})





local player = game.Players.LocalPlayer
local toolName = "Speed Coil"
local equippedTool = nil
local aktif = false

-- Fungsi mengunci tool agar tidak bisa dilepas
local function lockForever()
	while aktif do
		local character = player.Character
		local backpack = player:FindFirstChild("Backpack")

		if character then
			-- Equip jika belum di tangan
			if not character:FindFirstChild(toolName) and backpack then
				local t = backpack:FindFirstChild(toolName)
				if t then
					t.Parent = character
					equippedTool = t
				end
			end

			-- Tool dicoba dilepas? Ambil lagi
			if equippedTool and equippedTool.Parent ~= character then
				pcall(function()
					equippedTool.Parent = character
				end)
			end
		end

		-- Jika tool dihapus
		if not equippedTool or not equippedTool:IsDescendantOf(game) then
			local b = player:FindFirstChild("Backpack")
			if b then
				local t = b:FindFirstChild(toolName)
				if t then
					t.Parent = player.Character
					equippedTool = t
				end
			end
		end

		task.wait(0.1)
	end
end

-- Saat respawn: hapus tool lama & equip baru
player.CharacterAdded:Connect(function(character)
	if aktif then
		task.wait(0.5)

		-- Hapus tool lama
		local oldTool = character:FindFirstChild(toolName)
		if oldTool then oldTool:Destroy() end

		-- Ambil tool baru dari Backpack
		local backpack = player:FindFirstChild("Backpack")
		if backpack then
			local newTool = backpack:FindFirstChild(toolName)
			if newTool then
				newTool.Parent = character
				equippedTool = newTool
			end
		end
	end
end)

-- Toggle (dengan unequip saat OFF)
AddToggle(visualTab, {
	Name = "loop Speed Coil",
	Callback = function(v)
		print("ESP aktif:", v)
		local character = player.Character or player.CharacterAdded:Wait()
		local backpack = player:WaitForChild("Backpack")

		if v then
			-- Equip jika belum ada
			if not character:FindFirstChild(toolName) then
				local tool = backpack:FindFirstChild(toolName)
				if tool then
					tool.Parent = character
					equippedTool = tool
				else
					pcall(function()
						game.StarterGui:SetCore("SendNotification", {
							Title = "speee coil not found!";
							Text = "you need buy speed coil!";
							Duration = 4;
						})
					end)
					return
				end
			end

			aktif = true
			lockForever()

		else
			-- Toggle OFF → Unequip dari tangan ke Backpack
			aktif = false

			if character:FindFirstChild(toolName) then
				local tool = character:FindFirstChild(toolName)
				pcall(function()
					tool.Parent = backpack
				end)
			end
		end
	end
})






AddToggle(miscTab, {
	Name = "Rejoin",
	Callback = function(v)
		print("rejoin:", v)
		if v then
			local TeleportService = game:GetService("TeleportService")
			local Players = game:GetService("Players")
			local player = Players.LocalPlayer

			local placeId = game.PlaceId
			local jobId = game.JobId

			-- Rejoin ke server yang sama
			TeleportService:TeleportToPlaceInstance(placeId, jobId, player)
		end
	end
})


AddToggle(miscTab, {
	Name = "server hop",
	Callback = function(v)
		print("server lain:", v)
		if v then
			local HttpService = game:GetService("HttpService")
			local TeleportService = game:GetService("TeleportService")
			local Players = game:GetService("Players")
			local player = Players.LocalPlayer

			-- Ambil daftar server publik
			local url = string.format("https://games.roblox.com/v1/games/%s/servers/Public?sortOrder=Asc&limit=100", game.PlaceId)

			pcall(function()
				local response = game:HttpGet(url)
				local data = HttpService:JSONDecode(response)

				for _, server in pairs(data.data) do
					if server.playing < server.maxPlayers and server.id ~= game.JobId then
						TeleportService:TeleportToPlaceInstance(game.PlaceId, server.id, player)
						break
					end
				end
			end)
		end
	end
})




AddToggle(miscTab, {
	Name = "leave",
	Callback = function(v)
		print("leave:", v)
		if v then
			-- Langsung leave dari game
			pcall(function()
				game:Shutdown()
			end)
		end
	end
})






-- TOGGLE BUKA GUI
local TweenService = game:GetService("TweenService")

-- TOMBOL UTAMA
local toggleBtn = Instance.new("ImageButton", gui)
toggleBtn.Name = "HoverButton"
toggleBtn.Size = UDim2.new(0, 55, 0, 55)
toggleBtn.Position = UDim2.new(0, 10, 0.2, 0)
toggleBtn.Image = "rbxassetid://121962590520433"
toggleBtn.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
toggleBtn.BackgroundTransparency = 0.7
toggleBtn.Active = true
toggleBtn.Draggable = true

-- Sudut membulat
Instance.new("UICorner", toggleBtn).CornerRadius = UDim.new(0, 9)

-- UIStroke putih (mati, tidak dinamis)
local stroke = Instance.new("UIStroke")
stroke.Parent = toggleBtn
stroke.Thickness = 2
stroke.Color = Color3.fromRGB(255, 255, 255)
stroke.Transparency = 0.3 -- sedikit halus, bisa ubah ke 0 kalau mau full terang
stroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border

-- Efek Hover membesar
toggleBtn.MouseEnter:Connect(function()
	TweenService:Create(toggleBtn, TweenInfo.new(0.15), {
		Size = UDim2.new(0, 60, 0, 60)
	}):Play()
end)

toggleBtn.MouseLeave:Connect(function()
	TweenService:Create(toggleBtn, TweenInfo.new(0.15), {
		Size = UDim2.new(0, 55, 0, 55)
	}):Play()
end)

-- TOGGLE BUKA GUI (jika pakai mainFrame)
local isOpen = false
toggleBtn.MouseButton1Click:Connect(function()
	isOpen = not isOpen
	mainFrame.Visible = isOpen
end)



switchTab("Main")
















-- Fungsi untuk proses BillboardGui
local function processBillboardIfNeeded(obj)
	if obj:IsA("BasePart") and obj.Name == "Main" then
		local parent = obj.Parent
		while parent do
			if parent:IsA("Folder") and parent.Name == "Purchases" then
				for _, child in ipairs(obj:GetChildren()) do
					if child:IsA("BillboardGui") then
						child.Size = UDim2.new(0, 180, 0, 150)
						child.MaxDistance = 80
						child.StudsOffset = Vector3.new(0, 5, 0)
						print("✅ BillboardGui diubah:", obj:GetFullName())
					end
				end
				break
			end
			parent = parent.Parent
		end
	end
end

-- Proses awal semua objek
for _, obj in ipairs(workspace:GetDescendants()) do
	processBillboardIfNeeded(obj)
end

-- Pantau objek baru yang masuk ke workspace
workspace.DescendantAdded:Connect(function(obj)
	processBillboardIfNeeded(obj)
end)
