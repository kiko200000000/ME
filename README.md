# ME
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()

local Window = Library.CreateLib("Prision Life Hub", "Sentinel")

local Tab = Window:NewTab("Main")
local MainSection = Tab:NewSection("Main")



local Tab = Window:NewTab("Player")
local PlayerSection = Tab:NewSection("Player")


local Tab = Window:NewTab("Help")
local HelpSection = Tab:NewSection("Help")

MainSection:NewButton("Hack PowerFull", "ButtonInfo", function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/XTheMasterX/Scripts/Main/PrisonLife", true))()
    
    print("Clicked")
end)

MainSection:NewDropdown("Give Gun", "guns gratis :)", {"M9", "Remington 870", "AK-47"}, function(v)
    local A_1 = game:GetService("Workspace")["Prison_ITEMS"].giver[v].ITEMPICKUP
    local Event = game:GetService("Workspace").Remote.ItemHandler
    Event:InvokeServer(A_1)
end)

PlayerSection:NewSlider("WalkSpeed", "te da mucha corridad", 500, 16, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)

PlayerSection:NewSlider("JumpPower", "mucha saltura", 500, 50, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.JumpPower = s
end)


HelpSection:NewTextBox("Crash", "Crashs a Person Nevermind kills", function(txt)
	print(txt)
end)


