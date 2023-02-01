local Moon;
local Job = game.JobId
local PlayerCount = #game.Players:GetPlayers()
if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Mirage Island")then
    Mirage = "True"
else
    Mirage = "False"
end
if game:GetService("Lighting").Sky.MoonTextureId=="http://www.roblox.com/asset/?id=9709149431" then
    Moon = "Full Moon 100%";
elseif game:GetService("Lighting").Sky.MoonTextureId=="http://www.roblox.com/asset/?id=9709149052" then
    Moon = "Full Moon 75%";
elseif game:GetService("Lighting").Sky.MoonTextureId=="http://www.roblox.com/asset/?id=9709143733" then
    Moon = "Full Moon 50%";
elseif game:GetService("Lighting").Sky.MoonTextureId=="http://www.roblox.com/asset/?id=9709150401" then
    Moon = "Full Moon 25%";
elseif game:GetService("Lighting").Sky.MoonTextureId=="http://www.roblox.com/asset/?id=9709149680" then
    Moon = "Full Moon 10%";
else
    Moon = "Full Moon 0%";
end
Infomation = game:GetService("MarketplaceService"):GetProductInfo(game.PlaceId)
NameGames = Infomation.Name
_G.wephook = "https://discord.com/api/webhooks/1069133140670566420/ynz1Tqoccg8FjrODSCpfDtkUa2z3HJbH1W5FWfyLGtfPd0xtuvUV_OplfK3QKNIu9gBB"
        if _G.wephook ~= "" then
            pcall(function()
                local url =
                _G.wephook
                local data = {
                  ["content"] = "",
                  ["embeds"] = {
                      {   
                          ["author"] = {
                              ["name"] = "Check Full Moon"
                          },
                          ["type"] = "rich",
                          ["title"] = "Discord: https://discord.gg/mzmMvMsrUM | Full Notify !!",
                          ["color"] = tonumber(0x78da),
                          ["fields"] = {
                              {
                                  ["name"] = "Moon Status:",
                                  ["value"] = "```"..Moon.."```"
                              },
                              {
                                  ["name"] = "Mirage Island Spawn:",
                                  ["value"] = "```"..Mirage.."```"
                              },
                              {
                                  ["name"] = "Players In Server:",
                                  ["value"] = "```"..PlayerCount.."/12".."```"
                              },
                              {
                                  ["name"] = "Job Id:",
                                  ["value"] = "```"..Job.."```"
                              },
                              {
                                  ["name"] = "Server JobId:",
                                  ["value"] = "```".."game.ReplicatedStorage['__ServerBrowser']:InvokeServer('teleport',"..Job..")".."```"
                              }
                          }
                      }
                  }
               }
               local newdata = game:GetService("HttpService"):JSONEncode(data)
               
               local headers = {
                  ["content-type"] = "application/json"
               }
               request = http_request or request or HttpPost or syn.request
               local abcdef = {Url = url, Body = newdata, Method = "POST", Headers = headers}
               request(abcdef)
            end)
            else
                print("Invaild Url")
        end
