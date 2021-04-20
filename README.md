# brandonharris.electronportfolio

Electron app built using the Vue CLI and node 12 on Windows 10.
    Dependancies used:
        vue-cli-plugin-electron-builder
        qrcode.vue
        axios
        html2pdf-jspdf2

    How to run this project:
        npm install
        npm run electron:serve

NOTICE: The API used for this project allocates a 500 per day hit limit and the QR codes auto refreash every 5 seconds. This rate can be lowered or disabled in the QRCodes.vue folder by increasing the refresh time or turning off the refresh. 
