✅ 1. Actualizá los paquetes e instalá dependencias necesarias:
bash
Copiar
Editar
sudo apt update
sudo apt install ca-certificates curl apt-transport-https lsb-release gnupg
✅ 2. Agregá la clave GPG de Microsoft:
bash
Copiar
Editar
curl -sL https://packages.microsoft.com/keys/microsoft.asc | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/microsoft.gpg
✅ 3. Agregá el repositorio de Azure CLI:
bash
Copiar
Editar
AZ_REPO=$(lsb_release -cs)
echo "deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ $AZ_REPO main" | sudo tee /etc/apt/sources.list.d/azure-cli.list
✅ 4. Instalá Azure CLI:
bash
Copiar
Editar
sudo apt update
sudo apt install azure-cli
✅ 5. Verificá que esté instalado:
bash
Copiar
Editar
az version
Con eso ya podés usar comandos como az login o az webapp deploy.
