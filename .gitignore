-- Serviços necessários
local Players = game:GetService("Players")
local TweenService = game:GetService("TweenService")
local CoreGui = game:GetService("CoreGui")

local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

-- Evita duplicação caso o script rode novamente
if playerGui:FindFirstChild("VoidHubGui") then
	playerGui.VoidHubGui:Destroy()
end

-- Criando a ScreenGui principal
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "VoidHubGui"
screenGui.IgnoreGuiInset = true
screenGui.ResetOnSpawn = false
screenGui.Parent = playerGui

------------------------------------------------------------------
-- 1. TELA DE INTRODUÇÃO (FADE IN / VOID SCRIPTS / FADE OUT)
------------------------------------------------------------------
local introFrame = Instance.new("Frame")
introFrame.Name = "IntroFrame"
introFrame.Size = UDim2.new(1, 0, 1, 0)
introFrame.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
introFrame.BackgroundTransparency = 1
introFrame.Parent = screenGui

local introText = Instance.new("TextLabel")
introText.Name = "IntroText"
introText.Size = UDim2.new(0, 400, 0, 100)
introText.AnchorPoint = Vector2.new(0.5, 0.5)
introText.Position = UDim2.new(0.5, 0, 0.5, 0)
introText.BackgroundTransparency = 1
introText.Text = "VOID SCRIPTS"
introText.TextColor3 = Color3.fromRGB(255, 255, 255)
introText.TextSize = 36
introText.Font = Enum.Font.GothamBold
introText.TextTransparency = 1
introText.Parent = introFrame

------------------------------------------------------------------
-- 2. MENU PRINCIPAL (VOID HUB v0.1)
------------------------------------------------------------------
local mainFrame = Instance.new("Frame")
mainFrame.Name = "MainFrame"
mainFrame.Size = UDim2.new(0, 650, 0, 400)
mainFrame.AnchorPoint = Vector2.new(0.5, 0.5)
mainFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
mainFrame.BackgroundColor3 = Color3.fromRGB(22, 22, 22)
mainFrame.BorderSizePixel = 0
mainFrame.Visible = false
mainFrame.Parent = screenGui

-- Arredondar cantos do menu principal
local mainCorner = Instance.new("UICorner")
mainCorner.CornerRadius = UDim.new(0, 8)
mainCorner.Parent = mainFrame

-- Barra Superior (TopBar)
local topBar = Instance.new("Frame")
topBar.Size = UDim2.new(1, 0, 0, 45)
topBar.BackgroundTransparency = 1
topBar.Parent = mainFrame

local titleLabel = Instance.new("TextLabel")
titleLabel.Size = UDim2.new(0, 200, 1, 0)
titleLabel.Position = UDim2.new(0, 15, 0, 0)
titleLabel.BackgroundTransparency = 1
titleLabel.Text = "Void Hub"
titleLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
titleLabel.TextSize = 16
titleLabel.Font = Enum.Font.GothamBold
titleLabel.TextXAlignment = Enum.TextXAlignment.Left
titleLabel.Parent = topBar

local versionLabel = Instance.new("TextLabel")
versionLabel.Size = UDim2.new(0, 200, 0, 20)
versionLabel.Position = UDim2.new(0, 15, 0, 25)
versionLabel.BackgroundTransparency = 1
versionLabel.Text = "versão v0.1 - Todos os direitos reservados"
versionLabel.TextColor3 = Color3.fromRGB(150, 150, 150)
versionLabel.TextSize = 11
versionLabel.Font = Enum.Font.Gotham
versionLabel.TextXAlignment = Enum.TextXAlignment.Left
versionLabel.Parent = topBar

-- Barra Lateral de Categorias (Sidebar)
local sidebar = Instance.new("ScrollingFrame")
sidebar.Size = UDim2.new(0, 180, 1, -45)
sidebar.Position = UDim2.new(0, 0, 0, 45)
sidebar.BackgroundTransparency = 1
sidebar.CanvasSize = UDim2.new(0, 0, 0, 400)
sidebar.ScrollBarThickness = 2
sidebar.Parent = mainFrame

local sidebarLayout = Instance.new("UIListLayout")
sidebarLayout.SortOrder = Enum.SortOrder.LayoutOrder
sidebarLayout.Padding = UDim.new(0, 4)
sidebarLayout.Parent = sidebar

-- Função auxiliar para criar botões da sidebar
local function createCategoryButton(name, order)
	local btn = Instance.new("TextButton")
	btn.Size = UDim2.new(1, -10, 0, 35)
	btn.Position = UDim2.new(0, 5, 0, 0)
	btn.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
	btn.BackgroundTransparency = 1
	btn.Text = "   " .. name
	btn.TextColor3 = Color3.fromRGB(180, 180, 180)
	btn.TextSize = 13
	btn.Font = Enum.Font.GothamMedium
	btn.TextXAlignment = Enum.TextXAlignment.Left
	btn.LayoutOrder = order
	btn.Parent = sidebar
	
	local corner = Instance.new("UICorner")
	corner.CornerRadius = UDim.new(0, 6)
	corner.Parent = btn
	
	return btn
end

-- Criando categorias baseadas na imagem de referência
createCategoryButton("👤 Jogador", 1)
createCategoryButton("👁 Visuais", 2)
createCategoryButton("⚡ Exploits", 3)
createCategoryButton(" destrucción (Destruição)", 4)
createCategoryButton("🛡 Combate", 5)
createCategoryButton("🚗 Veículos", 6)
createCategoryButton("⚔ Armas (BETA)", 7)
createCategoryButton("⚙ Configurações", 8)

-- Painel de Conteúdo (Direita)
local contentPanel = Instance.new("Frame")
contentPanel.Size = UDim2.new(1, -190, 1, -55)
contentPanel.Position = UDim2.new(0, 185, 0, 50)
contentPanel.BackgroundColor3 = Color3.fromRGB(28, 28, 28)
contentPanel.Parent = mainFrame

local contentCorner = Instance.new("UICorner")
contentCorner.CornerRadius = UDim.new(0, 6)
contentCorner.Parent = contentPanel

local contentLayout = Instance.new("UIListLayout")
contentLayout.SortOrder = Enum.SortOrder.LayoutOrder
contentLayout.Padding = UDim.new(0, 10)
contentLayout.Parent = contentPanel

local contentPadding = Instance.UIPadding
-- Adicionando um exemplo de item dentro do painel (Igual ao da foto: Lançar Veículos)
local sampleItem = Instance.new("Frame")
sampleItem.Size = UDim2.new(1, -20, 0, 50)
sampleItem.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
sampleItem.Parent = contentPanel

local itemCorner = Instance.new("UICorner")
itemCorner.CornerRadius = UDim.new(0, 6)
itemCorner.Parent = sampleItem

local itemTitle = Instance.new("TextLabel")
itemTitle.Size = UDim2.new(1, -60, 0, 20)
itemTitle.Position = UDim2.new(0, 15, 0, 8)
itemTitle.BackgroundTransparency = 1
itemTitle.Text = "Lançar Veículos"
itemTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
itemTitle.TextSize = 13
itemTitle.Font = Enum.Font.GothamBold
itemTitle.TextXAlignment = Enum.TextXAlignment.Left
itemTitle.Parent = sampleItem

local itemDesc = Instance.new("TextLabel")
itemDesc.Size = UDim2.new(1, -60, 0, 15)
itemDesc.Position = UDim2.new(0, 15, 0, 26)
itemDesc.BackgroundTransparency = 1
itemDesc.Text = "Clique: Segurar | Y: Lançar"
itemDesc.TextColor3 = Color3.fromRGB(150, 150, 150)
itemDesc.TextSize = 11
itemDesc.Font = Enum.Font.Gotham
itemDesc.TextXAlignment = Enum.TextXAlignment.Left
itemDesc.Parent = sampleItem

------------------------------------------------------------------
-- 3. ANIMAÇÃO DE FADE IN / OUT (TWEENS)
------------------------------------------------------------------
task.spawn(function()
	-- Fade In do fundo da intro
	TweenService:Create(introFrame, TweenInfo.new(0.8), {BackgroundTransparency = 0}):Play()
	-- Fade In do texto "VOID SCRIPTS"
	TweenService:Create(introText, TweenInfo.new(0.8), {TextTransparency = 0}):Play()
	
	task.wait(2.2) -- Tempo que o texto fica visível na tela
	
	-- Fade Out do texto
	TweenService:Create(introText, TweenInfo.new(0.8), {TextTransparency = 1}):Play()
	-- Fade Out do fundo da intro
	local fadeOutTween = TweenService:Create(introFrame, TweenInfo.new(0.8), {BackgroundTransparency = 1})
	fadeOutTween:Play()
	
	fadeOutTween.Completed:Wait()
	introFrame:Destroy() -- Remove a tela de intro da memória
	
	-- Exibe o menu principal do Void Hub
	mainFrame.Visible = true
	mainFrame.Size = UDim2.new(0, 600, 0, 350)
	mainFrame.BackgroundTransparency = 1
	
	-- Animação de surgimento suave do menu principal
	TweenService:Create(mainFrame, TweenInfo.new(0.5, Enum.EasingStyle.Back, Enum.EasingDirection.Out), {
		Size = UDim2.new(0, 650, 0, 400),
		BackgroundTransparency = 0
	}):Play()
end)
