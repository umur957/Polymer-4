# Polymer-4
git clone https://github.com/polymerdevs/testnet-challenge-3-template.git
cd testnet-challenge-3-template
cp .env.example .env
nano .env
# Her zamanki gibi base sepolia ve op sepolia keyleri alinsin, gerekli hazirliklar metamask private keyleri, metamaske op ve base sepolia faucetleri alinsin ve bu kisim doldurulsun

sudo add-apt-repository ppa:git-core/ppa
sudo apt update; apt install git
sudo apt install curl
curl -s https://deb.nodesource.com/setup_18.x | sudo bash
sudo apt install nodejs -y
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"

nvm
nvm install 20
nvm use 20
curl -L https://foundry.paradigm.xyz | bash
source /home/gitpod/.bashrc
foundryup

wget -qO - 'https://proget.makedeb.org/debian-feeds/prebuilt-mpr.pub' | gpg --dearmor | sudo tee /usr/share/keyrings/prebuilt-mpr-archive-keyring.gpg 1> /dev/null
echo "deb [arch=all,$(dpkg --print-architecture) signed-by=/usr/share/keyrings/prebuilt-mpr-archive-keyring.gpg] https://proget.makedeb.org prebuilt-mpr $(lsb_release -cs)" | sudo tee /etc/apt/sources.list.d/prebuilt-mpr.list
sudo apt update

sudo apt install just
just install

# confing.json dosyasinda Send packet ve sendUniverseal Packetteki optimism port Addreslerini  0x691B9bB9f262f997263FBF47F968d2B08bb5a6B8  olarak degistirin

# Justfile a gelin ve alttaki kodlari en son satira ekleyin
run-challenge-4:
    echo "Running the challenge 4 flow..."
    just deploy base base
    just sanity-check
    just send-packet optimism
    echo "Thank you for participating in Challenge!"
    echo "Submit your evidence in the #proof channel in our Discord Server!"

# Contracts a girin ordan CCQueryUC.sol  dosyasina tiklayin ordaki onRecvUniversalPacket functionina alttaki yaziyi ekleyin
recvedPackets.push(UcPacketWithChannel(channelId, packet));

(address sender, string memory query) = abi.decode(packet.appData, (address, string));

bytes memory payload = abi.encode(sender, "mint");

return AckPacket(true, payload);
# Alttaki kodu yazin 
just run-challenge-4

# Sonuc olarak alttaki gibi bisey gorceksiniz.
![image](https://github.com/umur957/Polymer-4/assets/91764306/767063f1-684b-4007-908b-c6b3580e8b80)

# Simdi op explorera gidin : https://optimism-sepolia.blockscout.com/    addresinizi arayin, token transfere tiklayin eger Challenge 4 NFT with ID gorurseniz tamamsiniz, discorddaki sabitlenmis ornege bakarak gerekli bilgileri alin ve proof kanalina gonderin





