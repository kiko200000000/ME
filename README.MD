local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()

local Window = Library.CreateLib("Prision Life Hub", "Sentinel")

local Tab = Window:NewTab("Main")
local MainSection = Tab:NewSection("Main")



local Tab = Window:NewTab("Player")
local PlayerSection = Tab:NewSection("Player")


local Tab = Window:NewTab("Crash")
local CrashSection = Tab:NewSection("Crash")

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


CrashSection:NewTextBox("Crash", "Crashs a Person Nevermind kills", function(txt)
    game.StarterGui:SetCore("SendNotification", {
        Title = "Kill yourself";
        Text = "Loaded.";
        Duration = "10";
        })
        wait(1)
        game.StarterGui:SetCore("SendNotification", {
        Title = "Kill";
        Text = "Kill in 10 9 8 7 oh sorry the counter just stoped";
        Duration = "10";
        })
	print(txt)
end)

MainSection:NewDropdown("Gun Mod", "Makes the gun op", {"M9", "Remington 870", "AK-47"}, function(v)
    local module = nil
    if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(v) then
        module = require(game:GetService("Players").LocalPlayer.Backpack[v].GunStates)
    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild(v) then
        module = require(game:GetService("Players").LocalPlayer.Character[v].GunStates)
    end
    if module ~= nil then
        module["MaxAmmo"] = math.huge
        module["CurrentAmmo"] = math.huge
        module["StoredAmmo"] = math.huge
        module["FireRate"] = 0.000001
        module["Spread"] = 0
        module["Range"] = math.huge
        module["Bullets"] = 10
        module["ReloadTime"] = 0.000000
        module["AutoFire"] = true
    end
end)


MainSection:NewLabel("Thanks for using our script :)!")
