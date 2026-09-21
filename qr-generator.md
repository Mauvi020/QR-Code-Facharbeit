# QR-Code Generator

Gib einen Text oder eine URL ein:

<input
  id="qr-text"
  type="text"
  placeholder="https://example.com"
  style="width:100%;padding:10px;"
>

<button onclick="generateQR()">
  QR-Code erstellen
</button>

<div id="qrcode" style="margin-top:20px;"></div>

<script src="https://cdn.jsdelivr.net/npm/qrcodejs@1.0.0/qrcode.min.js"></script>

<script>
function generateQR() {
    const text = document.getElementById("qr-text").value;
    const container = document.getElementById("qrcode");

    if (!text) {
        alert("Bitte Text oder URL eingeben.");
        return;
    }

    container.innerHTML = "";

    new QRCode(container, {
        text: text,
        width: 256,
        height: 256,
        correctLevel: QRCode.CorrectLevel.H
    });
}
</script>
