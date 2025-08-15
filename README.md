game.Players.PlayerAdded:Connect(function(player)
	player.CharacterAdded:Connect(function(char)
		local root = char:WaitForChild("HumanoidRootPart")

		-- สร้างเงาปลานเบื้องหลัง
		local shadow = Instance.new("Part")
		shadow.Parent = workspace
		shadow.Anchored = true
		shadow.CanCollide = false
		shadow.Size = Vector3.new(2, 4, 2)
		shadow.Transparency = 0.6
		shadow.Material = Enum.Material.Neon
		shadow.Color = Color3.new(0,0,0)

		-- เสียงหลอนเบาๆ
		local sound = Instance.new("Sound", workspace)
		sound.SoundId = "rbxassetid://1837463327"
		sound.Looped = true
		sound.Volume = 2
		sound:Play()

		local loopActive = true
		player.AncestryChanged:Connect(function(_, parent)
			if not parent then
				loopActive = false
				shadow:Destroy()
				sound:Destroy()
			end
		end)

		while loopActive do
			if root.Parent == nil then break end

			-- ให้เงาติดตามผู้เล่นแบบลึกลับ
			local offset = Vector3.new(math.random(-2,2), math.random(0,2), math.random(-2,2))
			shadow.Position = root.Position + offset

			-- GUI ข้อความนักกลัว นักกลัว
			local gui = Instance.new("ScreenGui", player.PlayerGui)
			local label = Instance.new("TextLabel", gui)
			label.Size = UDim2.new(0.3,0,0.1,0)
			label.Position = UDim2.new(math.random(),0,math.random(),0)
			label.BackgroundTransparency = 1
			label.TextColor3 = Color3.new(1,0,0)
			label.Text = "i see you"
			label.TextScaled = true
			game:GetService("Debris"):AddItem(gui, 0.5)

task.wait(0.1)		
		end
	end)
end)
task.wait(20)
	while true do
		local b = Instance.new("Part")
		b.Parent = game.Workspace
		b.Size = Vector3.new(1, 1, 1)
		b.Position = Vector3.new(-8, 0.5, -30)

		print("heigfiwgfwigffgqpfgqfgifhgfiwhfiqwufheuififgqfgeifgwifughifgfipgiuwgfiwuegfiwegufwiefgweifugweifugefiuwegfiuwegfiweugfiweufgweifg")
		 -- รอหน่อยเพื่อไม่ให้ค้างเกม
	end

