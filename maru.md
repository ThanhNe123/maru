repeat task.wait(5) until game:IsLoaded(3)
repeat task.wait() until game.Players
repeat task.wait() until game.Players.LocalPlayer
repeat task.wait() until game.Players.LocalPlayer:FindFirstChild("PlayerGui")
repeat task.wait() until game.Players.LocalPlayer.PlayerGui:FindFirstChild("Main");
UserSettings():GetService('UserGameSettings').MasterVolume = 0;
settings().Rendering.QualityLevel = 1;
game:GetService("StarterGui"):SetCoreGuiEnabled(Enum.CoreGuiType.Chat,false)
game:GetService("StarterGui"):SetCoreGuiEnabled(Enum.CoreGuiType.PlayerList,false)
game:GetService("Lighting").GlobalShadows = false
for key, object in pairs(workspace:GetDescendants()) do
    if object:IsA("Part") or object:IsA("UnionOperation") or object:IsA("MeshPart") then
        object.Material = Enum.Material.SmoothPlastic
    elseif  (object:IsA("Texture") or object:IsA("Explosion") or object:IsA("ColorCorrectionEffect") or 
                object:IsA("Atmosphere") or object:IsA("SunRaysEffect") or object:IsA("BlurEffect") or 
                object:IsA("RainyStone") or object:IsA("Weather")  or object:IsA("BloomEffect")
                or object:IsA("Lighting") or object:IsA("FogEnd") or object:IsA("DepthOfFieldEffect")) then
        object:Destroy()
    end
end
_G.Team = "Pirate" -- Marine / Pirate
_G.KAITUN_SCRIPT = true
_G.LogsDes = {
    ["Enabled"] = false, -- เปิดการใช้งาน
    ["SendAlias"] = false, -- เปิดการส่ง Alias
    ["SendDescription"] = false, -- เปิดการส่ง Des
    ["DelaySend"] = 5 -- วินาที
}
_G.WebHook = {
    ["Enabled"] = false, -- เปิดการใช้งาน
    ["Url"] = "", -- ลิ้งค์เว็บฮุก
    ["Delay"] = 60 -- วินาที
}
_G.MainSettings = {
        ["EnabledHOP"] = false, -- เปิด HOP ( มันไม่มีอยู่ละใส่มาเท่ๆ )
        ['FPSBOOST'] = true, -- ภาพกาก
        ["FPSLOCKAMOUNT"] = 20, -- จำนวน FPS
        ['WhiteScreen'] = true, -- จอขาว
        ['CloseUI'] = true, -- ปิด Ui
        ["NotifycationExPRemove"] = true, -- ลบ ExP ที่เด้งตอนฆ่ามอน
        ['AFKCheck'] = 540, -- ถ้ายืนนิ่งเกินวิที่ตั้งมันจะรีเกม
        ["LockFragments"] = 22000, -- ล็อคเงินม่วง
        ["LockFruitsRaid"] = { -- ล็อคผลที่ไม่เอาไปลงดัน
            [1] = "Dough-Dough",
            [2] = "Dragon-Dragon",
            [3] = "Mammoth-Mammoth",
            [4] = "Leopard-Leopard",
            [5] = "Sound-Sound",
            [6] = "Shadow-Shadow",
            [7] = "Control-Control",
            [8] = "Spirit-Spirit",
            [9] = "Venom-Venom",
            [10] = "Gravity-Gravity",
            [11] = "Buddha-Buddha",
            [12] = "Love-Love",
            [13] = "Rumble-Rumble",
            [14] = "Portal-Portal",
            [15] = "Quake-Quake",
            [16] = "Blizzard-Blizzard",
        }
    }
_G.Fruits_Settings = { -- ตั้งค่าผล
    ['Main_Fruits'] = {'Dough-Dough'}, -- ผลหลัก ถ้ายังไม่ใช่ค่าที่ตั้งมันจะกินจนกว่าจะใช่หรือซื้อ
    ['Select_Fruits'] = {"Magma-Magma", "Ice-Ice", "Flame-Flame", "Leopard-Leopard"} -- กินหรือซื้อตอนไม่มีผล
}
_G.Quests_Settings = { -- ตั้งค่าเควสหลักๆ
    ['Rainbow_Haki'] = false,
    ["MusketeerHat"] = true,
    ["PullLever"] = false,
    ['DoughQuests_Mirror'] = {
        ['Enabled'] = true,
        ['UseFruits'] = true,
    }        
}
_G.Races_Settings = { -- ตั้งค่าเผ่า
    ['Race'] = {
        ['EnabledEvo'] = false,
        ["v2"] = true,
        ["v3"] = true,
        ["Races_Lock"] = {
            ["Races"] = { -- Select Races U want
                ["Mink"] = false,
                ["Human"] = true,
                ["Fishman"] = false,
            },
            ["RerollsWhenFragments"] = 20000 -- Random Races When Your Fragments is >= Settings
        }
    }
}
_G.Settings_Melee = { -- หมัดที่จะทำ
    ['Superhuman'] = true,
    ['DeathStep'] = true,
    ['SharkmanKarate'] = true,
    ['ElectricClaw'] = true,
    ['DragonTalon'] = true,
    ['Godhuman'] = true,
}
_G.FarmMastery_Settings = {
    ['Melee'] = false,
    ['Sword'] = false,
    ['DevilFruits'] = false,
    ['Select_Swords'] = {
        ["AutoSettings"] = true, -- ถ้าเปิดอันนี้มันจะเลือกดาบให้เองหรือฟาร์มทุกดาบนั่นเอง
        ["ManualSettings"] = { -- ถ้าปรับ AutoSettings เป็น false มันจะฟาร์มดาบที่เลือกตรงนี้ ตัวอย่างข้างล่าง
            "Tushita",
            "Yama"
        }
    }
}
_G.SwordSettings = { -- ดาบที่จะทำ
    ['Saber'] = true,
    ["Pole"] = false,
    ['MidnightBlade'] = false,
    ['Shisui'] = false,
    ['Saddi'] = false,
    ['Wando'] = false,
    ['Yama'] = true,
    ['Rengoku'] = false,
    ['Canvander'] = false,
    ['BuddySword'] = false,
    ['TwinHooks'] = false,
    ['HallowScryte'] = false,
    ['TrueTripleKatana'] = false,
    ['CursedDualKatana'] = true,
}
_G.GunSettings = { -- ปืนที่จะทำ
    ['Kabucha'] = false,
    ['SerpentBow'] = false,
    ['SoulGuitar'] = false,
}
getgenv().Key = "MARU-HC2E-BQPPF-KZSV-SUXNH-805T"
getgenv().id = "927036058636533800"
getgenv().Script_Mode = "Kaitun_Script"
loadstring(game:HttpGet("https://raw.githubusercontent.com/xshiba/MaruBitkub/main/Mobile.lua"))()
