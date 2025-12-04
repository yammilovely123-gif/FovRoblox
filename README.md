local MIN_FOV = 60
local MAX_FOV = 120

-- Função para alterar o FOV
local function setFOV(value)
    if typeof(value) ~= "number" then
        warn("O FOV deve ser um número!")
        return
    end
    if value < MIN_FOV or value > MAX_FOV then
        warn("O FOV deve estar entre " .. MIN_FOV .. " e " .. MAX_FOV)
        return
    end
    local player = game.Players.LocalPlayer
    if not player then return end

    local camera = workspace.CurrentCamera
    if camera then
        camera.FieldOfView = value
        print("Campo de Visão alterado para:", value)
    end
end

-- Exemplo de uso: altere o valor para modificar o FOV
local meuFOV = 100
setFOV(meuFOV)
