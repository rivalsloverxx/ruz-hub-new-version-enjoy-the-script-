-- ========================================================================================================================
-- RIVALS HUB | ENTERPRISE EDITION v6.0.0 (CAT BACKGROUND EDITION)
-- TARGET EXECUTOR: CLIENT-SIDE LOCALSTUDIO / EXECUTOR RUNTIME
-- ARCHITECTURE: OBJECT-ORIENTED MODULAR COMPONENT SYSTEM & SECURE GATEWAY
-- ========================================================================================================================

-- [[ CUSTOM BACKGROUND IMAGE ID SETUP ]]
-- Roblox Creator Dashboard'a yüklediğin görselin ID'sini buraya yapıştır:
local CUSTOM_BACKGROUND_ID = "rbxassetid://YOUR_IMAGE_ASSET_ID" 

-- [[ SECTION 1: SYSTEM SERVICES & DEPENDENCIES INJECTION ]]
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")
local Lighting = game:GetService("Lighting")
local CoreGui = game:GetService("CoreGui")
local StarterGui = game:GetService("StarterGui")

-- [[ SECTION 2: LOCAL PLAYER CONTEXT ]]
local LocalPlayer = Players.LocalPlayer
if not LocalPlayer then
    repeat task.wait() until Players.LocalPlayer
    LocalPlayer = Players.LocalPlayer
end

-- [[ SECTION 3: KEY SYSTEM CONFIGURATION ]]
local KeySystemConfig = {
    TargetKey = "AtezHub003",
    KeyLink = "https://atezkey.netlify.app"
}

-- [[ SECTION 4: COLOR PALETTES & GRAPHICAL DESIGN TOKENS ]]
local Theme = {
    WindowBackground   = Color3.fromRGB(11, 11, 15),
    SidebarBackground  = Color3.fromRGB(16, 16, 22),
    CardBackground     = Color3.fromRGB(22, 22, 30),
    CardBorder         = Color3.fromRGB(35, 35, 48),
    PrimaryAccent      = Color3.fromRGB(255, 35, 75),
    PrimaryGlow        = Color3.fromRGB(255, 80, 120),
    TextActive         = Color3.fromRGB(250, 250, 255),
    TextInactive       = Color3.fromRGB(140, 140, 155),
    TextSubtle         = Color3.fromRGB(85, 85, 100),
    SuccessState       = Color3.fromRGB(0, 230, 120),
    ErrorState         = Color3.fromRGB(255, 60, 60),
    ToggleInactive     = Color3.fromRGB(35, 35, 46)
}

-- [[ SECTION 5: DOM HELPER FACTORY FUNCTIONS ]]
local UIBuilder = {}

function UIBuilder.CreateCorner(radius, parent)
    local corner = Instance.new("UICorner")
    corner.CornerRadius = UDim.new(0, radius)
    corner.Parent = parent
    return corner
end

function UIBuilder.CreateStroke(color, thickness, parent, applyMode)
    local stroke = Instance.new("UIStroke")
    stroke.Color = color
    stroke.Thickness = thickness
    stroke.ApplyStrokeMode = applyMode or Enum.ApplyStrokeMode.Border
    stroke.Parent = parent
    return stroke
end

-- [[ SECTION 6: SCREEN GUI INITIATOR ]]
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "RivalsHub_Enterprise_CatEdition"
ScreenGui.ResetOnSpawn = false

pcall(function()
    ScreenGui.Parent = CoreGui
end)
if not ScreenGui.Parent then
    ScreenGui.Parent = LocalPlayer:WaitForChild("PlayerGui")
end

-- ========================================================================================================================
-- [KEY SYSTEM INTERFACE FRAMEWORK]
-- ========================================================================================================================

local KeyFrame = Instance.new("Frame")
KeyFrame.Name = "KeyFrame"
KeyFrame.Size = UDim2.new(0, 460, 0, 310)
KeyFrame.Position = UDim2.new(0.5, -230, 0.5, -155)
KeyFrame.BackgroundColor3 = Theme.WindowBackground
KeyFrame.BorderSizePixel = 0
KeyFrame.Active = true
KeyFrame.Draggable = true
KeyFrame.ClipsDescendants = true
KeyFrame.Parent = ScreenGui

UIBuilder.CreateCorner(16, KeyFrame)
local KeyStroke = UIBuilder.CreateStroke(Theme.PrimaryAccent, 2, KeyFrame)

task.spawn(function()
    while KeyFrame and KeyFrame.Parent do
        TweenService:Create(KeyStroke, TweenInfo.new(2, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut), {Color = Theme.PrimaryGlow}):Play()
        task.wait(2)
        TweenService:Create(KeyStroke, TweenInfo.new(2, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut), {Color = Theme.PrimaryAccent}):Play()
        task.wait(2)
    end
end)

local KeyHeaderBar = Instance.new("Frame")
KeyHeaderBar.Size = UDim2.new(1, 0, 0, 4)
KeyHeaderBar.BackgroundColor3 = Theme.PrimaryAccent
KeyHeaderBar.BorderSizePixel = 0
KeyHeaderBar.Parent = KeyFrame

local KeyTitle = Instance.new("TextLabel")
KeyTitle.Size = UDim2.new(1, 0, 0, 30)
KeyTitle.Position = UDim2.new(0, 0, 0, 18)
KeyTitle.Text = "RIVALS HUB GATEWAY"
KeyTitle.TextColor3 = Theme.PrimaryAccent
KeyTitle.TextSize = 18
KeyTitle.Font = Enum.Font.GothamBold
KeyTitle.BackgroundTransparency = 1
KeyTitle.Parent = KeyFrame

local KeySubtitle = Instance.new("TextLabel")
KeySubtitle.Size = UDim2.new(1, -40, 0, 20)
KeySubtitle.Position = UDim2.new(0, 20, 0, 48)
KeySubtitle.Text = "License System • Enter Your Key Below"
KeySubtitle.TextColor3 = Theme.TextSubtle
KeySubtitle.TextSize = 10
KeySubtitle.Font = Enum.Font.GothamSemibold
KeySubtitle.BackgroundTransparency = 1
KeySubtitle.Parent = KeyFrame

local LinkBanner = Instance.new("TextButton")
LinkBanner.Size = UDim2.new(1, -50, 0, 34)
LinkBanner.Position = UDim2.new(0, 25, 0, 78)
LinkBanner.BackgroundColor3 = Color3.fromRGB(18, 18, 26)
LinkBanner.Text = "  🔗 Get Key: " .. KeySystemConfig.KeyLink
LinkBanner.TextColor3 = Theme.PrimaryGlow
LinkBanner.TextSize = 11
LinkBanner.Font = Enum.Font.GothamBold
LinkBanner.TextXAlignment = Enum.TextXAlignment.Left
LinkBanner.AutoButtonColor = true
LinkBanner.Parent = KeyFrame

UIBuilder.CreateCorner(8, LinkBanner)
local LinkStroke = UIBuilder.CreateStroke(Theme.CardBorder, 1, LinkBanner)

LinkBanner.MouseButton1Click:Connect(function()
    if setclipboard then
        setclipboard(KeySystemConfig.KeyLink)
        LinkBanner.Text = "  ✅ Link Copied to Clipboard!"
        LinkBanner.TextColor3 = Theme.SuccessState
        TweenService:Create(LinkStroke, TweenInfo.new(0.2), {Color = Theme.SuccessState}):Play()
        task.wait(2)
        LinkBanner.Text = "  🔗 Get Key: " .. KeySystemConfig.KeyLink
        LinkBanner.TextColor3 = Theme.PrimaryGlow
        TweenService:Create(LinkStroke, TweenInfo.new(0.2), {Color = Theme.CardBorder}):Play()
    end
end)

local InputContainer = Instance.new("Frame")
InputContainer.Size = UDim2.new(1, -50, 0, 44)
InputContainer.Position = UDim2.new(0, 25, 0, 124)
InputContainer.BackgroundColor3 = Theme.CardBackground
InputContainer.Parent = KeyFrame

UIBuilder.CreateCorner(8, InputContainer)
local InputStroke = UIBuilder.CreateStroke(Theme.CardBorder, 1, InputContainer)

local KeyInputBox = Instance.new("TextBox")
KeyInputBox.Size = UDim2.new(1, -20, 1, 0)
KeyInputBox.Position = UDim2.new(0, 10, 0, 0)
KeyInputBox.PlaceholderText = "Paste License Key Here..."
KeyInputBox.PlaceholderColor3 = Theme.TextInactive
KeyInputBox.Text = ""
KeyInputBox.TextColor3 = Theme.TextActive
KeyInputBox.TextSize = 13
KeyInputBox.Font = Enum.Font.GothamSemibold
KeyInputBox.BackgroundTransparency = 1
KeyInputBox.ClearTextOnFocus = false
KeyInputBox.Parent = InputContainer

KeyInputBox.Focused:Connect(function()
    TweenService:Create(InputStroke, TweenInfo.new(0.2), {Color = Theme.PrimaryAccent}):Play()
end)

KeyInputBox.FocusLost:Connect(function()
    TweenService:Create(InputStroke, TweenInfo.new(0.2), {Color = Theme.CardBorder}):Play()
end)

local StatusLabel = Instance.new("TextLabel")
StatusLabel.Size = UDim2.new(1, 0, 0, 20)
StatusLabel.Position = UDim2.new(0, 0, 0, 176)
StatusLabel.Text = ""
StatusLabel.TextColor3 = Theme.TextSubtle
StatusLabel.TextSize = 11
StatusLabel.Font = Enum.Font.Gotham
StatusLabel.BackgroundTransparency = 1
StatusLabel.Parent = KeyFrame

local ButtonContainer = Instance.new("Frame")
ButtonContainer.Size = UDim2.new(1, -50, 0, 46)
ButtonContainer.Position = UDim2.new(0, 25, 0, 204)
ButtonContainer.BackgroundTransparency = 1
ButtonContainer.Parent = KeyFrame

local GetLinkBtn = Instance.new("TextButton")
GetLinkBtn.Size = UDim2.new(0.48, 0, 1, 0)
GetLinkBtn.Position = UDim2.new(0, 0, 0, 0)
GetLinkBtn.Text = "COPY LINK"
GetLinkBtn.TextColor3 = Theme.TextActive
GetLinkBtn.BackgroundColor3 = Theme.CardBackground
GetLinkBtn.Font = Enum.Font.GothamBold
GetLinkBtn.TextSize = 11
GetLinkBtn.Parent = ButtonContainer

UIBuilder.CreateCorner(8, GetLinkBtn)
local GetLinkStroke = UIBuilder.CreateStroke(Theme.CardBorder, 1, GetLinkBtn)

local RedeemBtn = Instance.new("TextButton")
RedeemBtn.Size = UDim2.new(0.48, 0, 1, 0)
RedeemBtn.Position = UDim2.new(0.52, 0, 0, 0)
RedeemBtn.Text = "UNLOCK HUB"
RedeemBtn.TextColor3 = Theme.TextActive
RedeemBtn.BackgroundColor3 = Theme.PrimaryAccent
RedeemBtn.Font = Enum.Font.GothamBold
RedeemBtn.TextSize = 11
RedeemBtn.Parent = ButtonContainer

UIBuilder.CreateCorner(8, RedeemBtn)
local RedeemStroke = UIBuilder.CreateStroke(Theme.PrimaryGlow, 1, RedeemBtn)

local function AddButtonAnimations(btn, defaultColor, hoverColor)
    btn.MouseEnter:Connect(function()
        TweenService:Create(btn, TweenInfo.new(0.2), {BackgroundColor3 = hoverColor}):Play()
    end)
    btn.MouseLeave:Connect(function()
        TweenService:Create(btn, TweenInfo.new(0.2), {BackgroundColor3 = defaultColor}):Play()
    end)
end

AddButtonAnimations(GetLinkBtn, Theme.CardBackground, Color3.fromRGB(30, 30, 42))
AddButtonAnimations(RedeemBtn, Theme.PrimaryAccent, Color3.fromRGB(255, 60, 100))

GetLinkBtn.MouseButton1Click:Connect(function()
    if setclipboard then
        setclipboard(KeySystemConfig.KeyLink)
        StatusLabel.Text = "Link copied to clipboard!"
        StatusLabel.TextColor3 = Theme.SuccessState
    else
        StatusLabel.Text = "Link: " .. KeySystemConfig.KeyLink
        StatusLabel.TextColor3 = Theme.PrimaryAccent
    end
    task.wait(2.5)
    StatusLabel.Text = ""
end)

local MainFrame = nil

RedeemBtn.MouseButton1Click:Connect(function()
    local userEntry = KeyInputBox.Text
    if userEntry == KeySystemConfig.TargetKey then
        StatusLabel.Text = "Key Accepted! Loading Rivals Hub..."
        StatusLabel.TextColor3 = Theme.SuccessState
        TweenService:Create(InputStroke, TweenInfo.new(0.2), {Color = Theme.SuccessState}):Play()

        task.wait(1)
        TweenService:Create(KeyFrame, TweenInfo.new(0.5, Enum.EasingStyle.Back, Enum.EasingDirection.In), {
            Position = UDim2.new(0.5, -230, 1.2, 0)
        }):Play()

        task.wait(0.6)
        KeyFrame.Visible = false
        
        if MainFrame then
            MainFrame.Visible = true
        end

        pcall(function()
            StarterGui:SetCore("SendNotification", {
                Title = "RIVALS HUB",
                Text = "License Verified! Press [K] to toggle menu.",
                Duration = 5
            })
        end)
    else
        StatusLabel.Text = "Invalid License Key! Please try again."
        StatusLabel.TextColor3 = Theme.ErrorState
        TweenService:Create(InputStroke, TweenInfo.new(0.2), {Color = Theme.ErrorState}):Play()
        
        local originalPos = KeyFrame.Position
        for i = 1, 6 do
            KeyFrame.Position = originalPos + UDim2.new(0, (i % 2 == 0 and 5 or -5), 0, 0)
            task.wait(0.03)
        end
        KeyFrame.Position = originalPos
    end
end)

-- ========================================================================================================================
-- [MAIN RIVALS HUB FRAMEWORK ENGINE]
-- ========================================================================================================================

local SystemState = {
    Aimbot = {
        Enabled = false, SilentAim = false, FOVCheck = true, FOVRadius = 150, Smoothness = 0.12, TargetPart = "HumanoidRootPart", TeamCheck = false, WallCheck = true, Triggerbot = false, Crosshair = true, Prediction = 0.13
    },
    Visuals = {
        ESPNames = true, ESPBoxes = true, ESPTracers = true, ESPDistance = true, ESPHighlight = true, HealthBar = true, TracersColor = Color3.fromRGB(255, 35, 75), HighlightColor = Color3.fromRGB(255, 35, 75)
    },
    Movement = {
        SpeedHack = false, WalkSpeed = 36, JumpPowerHack = false, JumpPower = 110, InfiniteJump = false, Noclip = false, Fly = false, AutoClicker = false
    },
    World = {
        FullBright = false, FOVChanger = false, FieldOfView = 95, AntiAFK = true, NoFog = true
    }
}

MainFrame = Instance.new("Frame")
MainFrame.Name = "MainFrame"
MainFrame.Size = UDim2.new(0, 760, 0, 500)
MainFrame.Position = UDim2.new(0.5, -380, 0.5, -250)
MainFrame.BackgroundColor3 = Theme.WindowBackground
MainFrame.BorderSizePixel = 0
MainFrame.Active = true
MainFrame.Draggable = true
MainFrame.ClipsDescendants = true
MainFrame.Visible = false
MainFrame.Parent = ScreenGui

UIBuilder.CreateCorner(14, MainFrame)
local MainStroke = UIBuilder.CreateStroke(Theme.PrimaryAccent, 2, MainFrame)

-- [[ BACKGROUND IMAGE INTEGRATION ]]
local MenuBackgroundImage = Instance.new("ImageLabel")
MenuBackgroundImage.Name = "MenuBackgroundImage"
MenuBackgroundImage.Size = UDim2.new(1, 0, 1, 0)
MenuBackgroundImage.Position = UDim2.new(0, 0, 0, 0)
MenuBackgroundImage.BackgroundTransparency = 1
MenuBackgroundImage.Image = CUSTOM_BACKGROUND_ID
MenuBackgroundImage.ImageTransparency = 0.35 -- Yazıların rahat okunması için koyulaştırılmış şeffaflık
MenuBackgroundImage.ScaleType = Enum.ScaleType.Crop
MenuBackgroundImage.ZIndex = 0
MenuBackgroundImage.Parent = MainFrame

UIBuilder.CreateCorner(14, MenuBackgroundImage)

task.spawn(function()
    while task.wait(2) do
        TweenService:Create(MainStroke, TweenInfo.new(2, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut), {Color = Theme.PrimaryGlow}):Play()
        task.wait(2)
        TweenService:Create(MainStroke, TweenInfo.new(2, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut), {Color = Theme.PrimaryAccent}):Play()
    end
end)

local Sidebar = Instance.new("Frame")
Sidebar.Name = "Sidebar"
Sidebar.Size = UDim2.new(0, 200, 1, 0)
Sidebar.BackgroundColor3 = Theme.SidebarBackground
Sidebar.BackgroundTransparency = 0.25 -- Arka plan görselinin hafifçe gözükmesi için
Sidebar.BorderSizePixel = 0
Sidebar.ZIndex = 2
Sidebar.Parent = MainFrame

UIBuilder.CreateCorner(14, Sidebar)

local LogoHeaderContainer = Instance.new("Frame")
LogoHeaderContainer.Size = UDim2.new(1, 0, 0, 75)
LogoHeaderContainer.BackgroundTransparency = 1
LogoHeaderContainer.ZIndex = 2
LogoHeaderContainer.Parent = Sidebar

local LogoTitleLabel = Instance.new("TextLabel")
LogoTitleLabel.Size = UDim2.new(1, -20, 0, 30)
LogoTitleLabel.Position = UDim2.new(0, 18, 0, 18)
LogoTitleLabel.Text = "RIVALS HUB"
LogoTitleLabel.TextColor3 = Theme.PrimaryAccent
LogoTitleLabel.TextSize = 22
LogoTitleLabel.Font = Enum.Font.GothamBold
LogoTitleLabel.TextXAlignment = Enum.TextXAlignment.Left
LogoTitleLabel.BackgroundTransparency = 1
LogoTitleLabel.ZIndex = 2
LogoTitleLabel.Parent = LogoHeaderContainer

local LogoSubtitleLabel = Instance.new("TextLabel")
LogoSubtitleLabel.Size = UDim2.new(1, -20, 0, 15)
LogoSubtitleLabel.Position = UDim2.new(0, 18, 0, 46)
LogoSubtitleLabel.Text = "ENTERPRISE EDITION v6.0"
LogoSubtitleLabel.TextColor3 = Theme.TextSubtle
LogoSubtitleLabel.TextSize = 9
LogoSubtitleLabel.Font = Enum.Font.GothamBold
LogoSubtitleLabel.TextXAlignment = Enum.TextXAlignment.Left
LogoSubtitleLabel.BackgroundTransparency = 1
LogoSubtitleLabel.ZIndex = 2
LogoSubtitleLabel.Parent = LogoHeaderContainer

local NavigationTabHolder = Instance.new("Frame")
NavigationTabHolder.Size = UDim2.new(1, -20, 1, -160)
NavigationTabHolder.Position = UDim2.new(0, 10, 0, 85)
NavigationTabHolder.BackgroundTransparency = 1
NavigationTabHolder.ZIndex = 2
NavigationTabHolder.Parent = Sidebar

local NavigationListLayout = Instance.new("UIListLayout")
NavigationListLayout.SortOrder = Enum.SortOrder.LayoutOrder
NavigationListLayout.Padding = UDim.new(0, 6)
NavigationListLayout.Parent = NavigationTabHolder

local PageContentHolder = Instance.new("Frame")
PageContentHolder.Size = UDim2.new(1, -215, 1, -20)
PageContentHolder.Position = UDim2.new(0, 208, 0, 10)
PageContentHolder.BackgroundTransparency = 1
PageContentHolder.ZIndex = 2
PageContentHolder.Parent = MainFrame

local CategoryPages = {}

local function BuildCategoryPage(pageName)
    local pageScroll = Instance.new("ScrollingFrame")
    pageScroll.Name = pageName .. "Page"
    pageScroll.Size = UDim2.new(1, -5, 1, 0)
    pageScroll.BackgroundTransparency = 1
    pageScroll.ScrollBarThickness = 4
    pageScroll.ScrollBarImageColor3 = Theme.PrimaryAccent
    pageScroll.CanvasSize = UDim2.new(0, 0, 0, 0)
    pageScroll.Visible = false
    pageScroll.ZIndex = 2
    pageScroll.Parent = PageContentHolder

    local pageGrid = Instance.new("UIGridLayout")
    pageGrid.CellSize = UDim2.new(0, 252, 0, 52)
    pageGrid.CellPadding = UDim2.new(0, 12, 0, 12)
    pageGrid.Parent = pageScroll

    pageGrid:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
        pageScroll.CanvasSize = UDim2.new(0, 0, 0, pageGrid.AbsoluteContentSize.Y + 15)
    end)

    CategoryPages[pageName] = pageScroll
    return pageScroll
end

local function BuildCategoryTabButton(tabName, iconGraphic)
    local btn = Instance.new("TextButton")
    btn.Size = UDim2.new(1, 0, 0, 40)
    btn.Text = "    " .. iconGraphic .. "   " .. tabName
    btn.TextColor3 = Theme.TextInactive
    btn.BackgroundColor3 = Color3.fromRGB(18, 18, 25)
    btn.Font = Enum.Font.GothamBold
    btn.TextSize = 12
    btn.TextXAlignment = Enum.TextXAlignment.Left
    btn.ZIndex = 2
    btn.Parent = NavigationTabHolder

    UIBuilder.CreateCorner(8, btn)

    btn.MouseButton1Click:Connect(function()
        for pageKey, pageInstance in pairs(CategoryPages) do
            pageInstance.Visible = (pageKey == tabName)
        end
        for _, childButton in pairs(NavigationTabHolder:GetChildren()) do
            if childButton:IsA("TextButton") then
                TweenService:Create(childButton, TweenInfo.new(0.2), {BackgroundColor3 = Color3.fromRGB(18, 18, 25), TextColor3 = Theme.TextInactive}):Play()
            end
        end
        TweenService:Create(btn, TweenInfo.new(0.2), {BackgroundColor3 = Theme.PrimaryAccent, TextColor3 = Theme.TextActive}):Play()
    end)

    return btn
end

local CombatCategoryPage   = BuildCategoryPage("COMBAT")
local VisualsCategoryPage  = BuildCategoryPage("VISUALS")
local MovementCategoryPage = BuildCategoryPage("MOVEMENT")
local MiscCategoryPage     = BuildCategoryPage("MISC")

local CombatTabBtn   = BuildCategoryTabButton("COMBAT", "⚔")
local VisualsTabBtn  = BuildCategoryTabButton("VISUALS", "👁")
local MovementTabBtn = BuildCategoryTabButton("MOVEMENT", "⚡")
local MiscTabBtn     = BuildCategoryTabButton("MISC", "⚙")

CombatCategoryPage.Visible = true
CombatTabBtn.BackgroundColor3 = Theme.PrimaryAccent
CombatTabBtn.TextColor3 = Theme.TextActive

local function AttachToggleCard(targetPage, cardTitle, cardDescription, stateTableRef, stateKey)
    local cardFrame = Instance.new("Frame")
    cardFrame.BackgroundColor3 = Theme.CardBackground
    cardFrame.BackgroundTransparency = 0.2 -- Fotoğrafın kartların arkasından hafifçe belirmesi için
    cardFrame.ZIndex = 2
    cardFrame.Parent = targetPage

    UIBuilder.CreateCorner(8, cardFrame)
    local cardStroke = UIBuilder.CreateStroke(Theme.CardBorder, 1, cardFrame)

    local titleTextLabel = Instance.new("TextLabel")
    titleTextLabel.Size = UDim2.new(1, -60, 0, 20)
    titleTextLabel.Position = UDim2.new(0, 12, 0, 7)
    titleTextLabel.Text = cardTitle
    titleTextLabel.TextColor3 = Theme.TextActive
    titleTextLabel.TextSize = 11
    titleTextLabel.Font = Enum.Font.GothamBold
    titleTextLabel.TextXAlignment = Enum.TextXAlignment.Left
    titleTextLabel.BackgroundTransparency = 1
    titleTextLabel.ZIndex = 2
    titleTextLabel.Parent = cardFrame

    local descTextLabel = Instance.new("TextLabel")
    descTextLabel.Size = UDim2.new(1, -60, 0, 16)
    descTextLabel.Position = UDim2.new(0, 12, 0, 26)
    descTextLabel.Text = cardDescription
    descTextLabel.TextColor3 = Theme.TextSubtle
    descTextLabel.TextSize = 9
    descTextLabel.Font = Enum.Font.Gotham
    descTextLabel.TextXAlignment = Enum.TextXAlignment.Left
    descTextLabel.BackgroundTransparency = 1
    descTextLabel.ZIndex = 2
    descTextLabel.Parent = cardFrame

    local switchTrack = Instance.new("Frame")
    switchTrack.Size = UDim2.new(0, 38, 0, 22)
    switchTrack.Position = UDim2.new(1, -48, 0.5, -11)
    switchTrack.BackgroundColor3 = stateTableRef[stateKey] and Theme.PrimaryAccent or Theme.ToggleInactive
    switchTrack.ZIndex = 2
    switchTrack.Parent = cardFrame

    UIBuilder.CreateCorner(100, switchTrack)

    local switchKnob = Instance.new("Frame")
    switchKnob.Size = UDim2.new(0, 18, 0, 18)
    switchKnob.Position = stateTableRef[stateKey] and UDim2.new(1, -20, 0.5, -9) or UDim2.new(0, 2, 0.5, -9)
    switchKnob.BackgroundColor3 = Theme.TextActive
    switchKnob.ZIndex = 2
    switchKnob.Parent = switchTrack

    UIBuilder.CreateCorner(100, switchKnob)

    local triggerButton = Instance.new("TextButton")
    triggerButton.Size = UDim2.new(1, 0, 1, 0)
    triggerButton.BackgroundTransparency = 1
    triggerButton.Text = ""
    triggerButton.ZIndex = 3
    triggerButton.Parent = cardFrame

    triggerButton.MouseButton1Click:Connect(function()
        stateTableRef[stateKey] = not stateTableRef[stateKey]
        local isEnabled = stateTableRef[stateKey]

        TweenService:Create(cardStroke, TweenInfo.new(0.2), {Color = isEnabled and Theme.PrimaryAccent or Theme.CardBorder}):Play()
        TweenService:Create(switchTrack, TweenInfo.new(0.2), {BackgroundColor3 = isEnabled and Theme.PrimaryAccent or Theme.ToggleInactive}):Play()
        TweenService:Create(switchKnob, TweenInfo.new(0.2), {
            Position = isEnabled and UDim2.new(1, -20, 0.5, -9) or UDim2.new(0, 2, 0.5, -9)
        }):Play()
    end)
end

AttachToggleCard(CombatCategoryPage, "Aimbot Lock", "Smooth target tracking lock", SystemState.Aimbot, "Enabled")
AttachToggleCard(CombatCategoryPage, "Silent Aim Logic", "Raycast redirect engine", SystemState.Aimbot, "SilentAim")
AttachToggleCard(CombatCategoryPage, "FOV Circle Overlay", "Render target lock radius", SystemState.Aimbot, "FOVCheck")
AttachToggleCard(CombatCategoryPage, "Team Check Filter", "Ignore allied team targets", SystemState.Aimbot, "TeamCheck")
AttachToggleCard(CombatCategoryPage, "Wall Check Validator", "Verify line-of-sight exposure", SystemState.Aimbot, "WallCheck")
AttachToggleCard(CombatCategoryPage, "Auto Triggerbot", "Instant fire on target cross", SystemState.Aimbot, "Triggerbot")

AttachToggleCard(VisualsCategoryPage, "Player Name Tags", "Render overhead username text", SystemState.Visuals, "ESPNames")
AttachToggleCard(VisualsCategoryPage, "3D Box Bounding", "Perspective bounding box", SystemState.Visuals, "ESPBoxes")
AttachToggleCard(VisualsCategoryPage, "Direction Tracers", "Draw lines to target positions", SystemState.Visuals, "ESPTracers")
AttachToggleCard(VisualsCategoryPage, "Distance Counters", "Real-time stud unit indicators", SystemState.Visuals, "ESPDistance")
AttachToggleCard(VisualsCategoryPage, "Health Bar Overlay", "Dynamic health tracking bar", SystemState.Visuals, "HealthBar")
AttachToggleCard(VisualsCategoryPage, "Neon Glow Chams", "Highlight models through walls", SystemState.Visuals, "ESPHighlight")

AttachToggleCard(MovementCategoryPage, "Velocity Speedhack", "Override player walk velocity", SystemState.Movement, "SpeedHack")
AttachToggleCard(MovementCategoryPage, "Jump Multiplier", "Custom jump height scaling", SystemState.Movement, "JumpPowerHack")
AttachToggleCard(MovementCategoryPage, "Infinite Air Jump", "Continuous air jump impulse", SystemState.Movement, "InfiniteJump")
AttachToggleCard(MovementCategoryPage, "Collision Bypass", "Pass through wall geometries", SystemState.Movement, "Noclip")
AttachToggleCard(MovementCategoryPage, "3D Character Flight", "Free fly across camera vectors", SystemState.Movement, "Fly")
AttachToggleCard(MovementCategoryPage, "Rapid Auto Clicker", "Automate mouse click sequence", SystemState.Movement, "AutoClicker")

AttachToggleCard(MiscCategoryPage, "Full Map Brightness", "Disable shadow and lighting limits", SystemState.World, "FullBright")
AttachToggleCard(MiscCategoryPage, "Camera FOV Override", "Extend camera field of view", SystemState.World, "FOVChanger")
AttachToggleCard(MiscCategoryPage, "Custom Crosshair", "Screen-centered precision cross", SystemState.Aimbot, "Crosshair")
AttachToggleCard(MiscCategoryPage, "Anti-AFK Protection", "Prevent idle disconnect kick", SystemState.World, "AntiAFK")
AttachToggleCard(MiscCategoryPage, "Third Person Lock", "Unlock camera zoom limits", SystemState.World, "ThirdPerson")
AttachToggleCard(MiscCategoryPage, "Clear Atmosphere Fog", "Remove fog render barriers", SystemState.World, "NoFog")

UserInputService.InputBegan:Connect(function(input, gameProcessed)
    if not gameProcessed and input.KeyCode == Enum.KeyCode.K then
        if MainFrame and MainFrame.Visible then
            MainFrame.Visible = not MainFrame.Visible
        end
    end
end)

RunService.RenderStepped:Connect(function()
    if not MainFrame.Visible and KeyFrame.Visible then return end
    
    if LocalPlayer.Character and LocalPlayer.Character:FindFirstChildOfClass("Humanoid") then
        local humanoid = LocalPlayer.Character:FindFirstChildOfClass("Humanoid")
        humanoid.WalkSpeed = SystemState.Movement.SpeedHack and SystemState.Movement.WalkSpeed or 16
        humanoid.JumpPower = SystemState.Movement.JumpPowerHack and SystemState.Movement.JumpPower or 50
    end

    if SystemState.World.FullBright then
        Lighting.Brightness = 2
        Lighting.ClockTime = 14
        Lighting.GlobalShadows = false
    end
end)
