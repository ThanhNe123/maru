_G.ModeSeletect = "Easy" -- Hard , Nightmare, Medium
wait(10)repeat wait() until game:IsLoaded()
function clickUI(a)
    (game:GetService("VirtualInputManager")):SendMouseButtonEvent(a.AbsolutePosition.X + a.AbsoluteSize.X / 2,
        a.AbsolutePosition.Y + 50, 0, true, a, 1);
    (game:GetService("VirtualInputManager")):SendMouseButtonEvent(a.AbsolutePosition.X + a.AbsoluteSize.X / 2,
        a.AbsolutePosition.Y + 50, 0, false, a, 1);
end;

if game.PlaceId == 13775256536 then
    local args = {
        [1] = {
            [1] = {
                [1] = "Trading",
                [2] = 3
            },
            [2] = "2o"
        }
    }

    game:GetService("ReplicatedStorage"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))
    wait(1)
    for i, v in pairs(workspace.Lifts.ToiletHQ:GetChildren()) do
        local a = string.split(v.BasePart.StatusGui.PlayersCount.Text, "/")
        if tonumber(a[1]) == 0 then
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Area.CFrame
            break
        end
    end
    spawn(function()
        while wait() do
            if game:GetService("Players").LocalPlayer.PlayerGui.Lobby.QueueFrame.Visible then
                clickUI(game:GetService("Players").LocalPlayer.PlayerGui.Lobby.QueueFrame.Start)
            end
        end
    end)
else
    spawn(function()
        while wait() do
            pcall(function()
                if game:GetService("Players").LocalPlayer.PlayerGui.Match.WaveInfo.AutoSkip.Visible then
                    if game.Players.LocalPlayer.PlayerGui.Match.WaveInfo.AutoSkip.OnAndOff.BackgroundColor3 == Color3.fromRGB(255, 0, 0) then
                        clickUI(game.Players.LocalPlayer.PlayerGui.Match.WaveInfo.AutoSkip.OnAndOff)
                    end
                    if game:GetService("Players").LocalPlayer.PlayerGui.VotingFrame.VoteFrame.Visible then
                        if _G.ModeSeletect == "Easy" then
                            clickUI(game:GetService("Players").LocalPlayer.PlayerGui.VotingFrame.VoteFrame.VoteMainFrame
                                .MainFrame
                                .Easy.Vote)
                        end
                        if _G.ModeSeletect == "Hard" then
                            clickUI(game:GetService("Players").LocalPlayer.PlayerGui.VotingFrame.VoteFrame.VoteMainFrame
                                .MainFrame
                                .Hard.Vote)
                        end
                        if _G.ModeSeletect == "Nightmare" then
                            clickUI(game:GetService("Players").LocalPlayer.PlayerGui.VotingFrame.VoteFrame.VoteMainFrame
                                .MainFrame
                                .Nightmare.Vote)
                        end
                        if _G.ModeSeletect == "Medium" then
                            clickUI(game:GetService("Players").LocalPlayer.PlayerGui.VotingFrame.VoteFrame.VoteMainFrame
                                .MainFrame
                                .Medium.Vote)
                        end
                    end
                    if game:GetService("Players").LocalPlayer.PlayerGui.Match.MatchFinish.Visible then
                        game:GetService("TeleportService"):Teleport(13775256536)
                    end
                end
            end)
        end
    end)
end
