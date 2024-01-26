---
title: Web Flasher
description: Firmware Web Installer for OpenDTU Firmware
---

<style>
  .md-content__button {
    display: none;
  }
  .pick-variant select {
    background: transparent;
    width: 300px;
    padding: 1px;
    font-size: 16pt;
    border: 1px solid #ddd;
    height: 51px;
    border-radius: 15px;
  }
  .invisible {
    visibility: hidden;
  }
  .radios li {
    list-style: none;
    line-height: 2em;
  }
</style>

# Web Flasher

Flash or Find your device using next options:

1. Plug in your ESP32 to a USB port.
2. Hit "Install" and select the correct COM port.
3. Get OpenDTU firmware installed and connected in less than 3 minutes!

<p>Select your product</p>
<ul class="radios">
<li>
    <label><input type="radio" name="type" value="esp32" /> ESP32</label>
</li>
<li>
    <label><input type="radio" name="type" value="esp32s3" /> ESP32S3</label>
</li>
<li>
    <label><input type="radio" name="type" value="esp32s3_usb" /> ESP32S3 with integrated USB connection</label>
</li>
</ul>
<p class="button-row" align="center">
<esp-web-install-button class="invisible">
  <button slot="activate" class="md-button md-button--primary">INSTALL</button>
  <span slot="unsupported">Use Chrome Desktop</span>
  <span slot="not-allowed">Not allowed to use this on HTTP!</span>
</esp-web-install-button>
</p>

Powered by [ESP Web Tools](https://esphome.github.io/esp-web-tools/){target=_blank}

<script>
    document.querySelectorAll('input[name="type"]').forEach(radio =>
    radio.addEventListener("change", () => {
        const button = document.querySelector('esp-web-install-button');
        button.manifest = `../files/manifest_${radio.value}.json`;
        button.classList.remove('invisible');
    }
    ));
</script>
<script type="module" src="https://unpkg.com/esp-web-tools@8.0.1/dist/web/install-button.js?module"></script>
