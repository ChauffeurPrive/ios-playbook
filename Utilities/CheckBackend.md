# Check what the backend is sending me

You need to see if the backend is sending proper data.

## Steps

1. Download and install [Charles](https://www.charlesproxy.com/download/).
2. In Charles, go to `Proxy > SSL Proxying Settings`.
3. In the tab `SSL Proxying`, add the following values :

```
Host: <ENVIRONMENT_HOSTNAME> - Port: 443
```

:bulb: : If you're testing on other environments, you will need to add the host and the port for them.

### Using Simulator

1. In Charles, go to `Help > SSL Proxying > Install Charles Root Certificate in iOS Simulators`.
2. In Simulator, go to `Settings > General > About > Certificate Trust Settings` and enable `Charles Proxy CA`.
3. Launch the app, you should see every requests the app is sending and their response.

### Using a device

1. On your device, go to http://www.charlesproxy.com/getssl to install Charles Certificate.
2. On your device, go to `Settings > General > About > Certificate Trust Settings` and enable `Charles Proxy CA`.
3. On your Mac, go to `Settings > Network`, select your Wi-Fi network and get your `IP Address`.
4. On your device, go to `Settings > Wi-Fi` and tap on the same Wi-Fi network than your Mac.
5. Go to `Configure Proxy` and set it to `Manual`. Type your `IP Address` from step 3 and `8888` as Port.
6. On your Mac, Charles should show you a pop up asking for your permission.
7. Launch the app, you should see every requests the app is sending and their response.
