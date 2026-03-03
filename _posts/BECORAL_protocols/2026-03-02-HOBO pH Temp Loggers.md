# HOBO pH & Temperature Loggers (MX2501), K. Cayemitte, May 16, 2025

[Omega HOBO Data Loggers Manual](https://manualspro.net/525242-hobo-mx2501-mx-ph-and-temperature-logger-user-guide?utm_source=chatgpt.com)

## Equipment and Materials

1. HOBO MX2501 Data Logger (includes pre-installed pH electrode submerged in storage solution)
2. HOBOconnect App (available for iOS, Android, and Windows)
3. Mobile Device or Windows PC with Bluetooth Low Energy (BLE) capability
4. pH Calibration Solutions: pH 4.01, 7.00, and 10.00 (e.g., MX2500-CAL-KIT)
5. Deionized or Distilled Water and a squirt bottle
6. Optional Accessories:
    A. Anti-biofouling copper guard
    B. Calibration beakers
    C. Replacement pH electrode (MX2500-ELECTRODE)
    D. Electrode storage solution (MX2500-STORE-SOLN)

## Pre-Deployment Preparation

### Install HOBOconnect App
1. Download and install the HOBOconnect app from the App Store, Google Play, or Onset’s website.
2. Enable Bluetooth on your device.

### Prepare the Logger
1. Unscrew and remove the clear storage cap containing the storage solution.
2. Rinse the pH sensor gently with deionized or distilled water.
3. Attach the closure cap to the logger.

### pH Calibration Procedure
*Calibration is essential before each deployment to ensure accurate pH measurements.*
1. Open the HOBOconnect app and connect to the logger.
2. Place the sensor in pH 7.00 buffer solution, ensuring the sensor end cap, temperature sensor, and closure cap are submerged.
3. Follow the app’s on-screen instructions to start calibration. Once the pH reading stabilizes, confirm the calibration.
4. Rinse the sensor with deionized water.
5. Repeat the calibration steps with pH 4.01 and/or 10.00 buffer solutions as needed.
6. After calibration, rinse the sensor again with deionized water.

*Note: Calibration should be performed using standard pH buffers. Custom buffers are not supported.*

### Logger Configuration
1. In the HOBOconnect app, configure the following settings:
    A. Logging Interval: 1 second to 18 hours.
    B. Start Mode: Immediate, push button, date & time, or next interval.
    C. Stop Mode: When memory is full, push button, date & time, or after a set logging period.
    D. Bluetooth Power Mode:
      D1. Always On: Bluetooth is continuously active.
      D2. Always Off: Bluetooth activates only when manually triggered.
      D3. Off Water Detect: Bluetooth activates when the logger is out of water.
2. Save the settings to the logger.

## Deployment, Data Retrieval, Maintenance, Specs

### Deployment
1. Remove the closure cap.
2. If biofouling is a concern, attach the anti-biofouling copper guard by aligning its holes with those on the sensor end cap and pH electrode.
3. Deploy the logger at the desired location, ensuring it is fully submerged.

*Note: The logger is waterproof up to 40 meters and suitable for both freshwater and saltwater environments.*

### Data Retrieval
1. Retrieve the logger from the deployment site.
2. If Bluetooth was set to "Always Off" or "Off Water Detect," activate it by pressing the switch on the logger or removing it from the water, respectively.
3. Open the HOBOconnect app and connect to the logger.
4. Download the recorded data.
5. Export the data in desired formats (CSV, TXT, XLSX, or HOBO files) for analysis.

### Post-Deployment Maintenance
1. Rinse the pH sensor with deionized water.
2. Reattach the clear storage cap filled with storage solution to maintain electrode hydration.
3. Store the logger in a cool, dry place until the next deployment.

*Note: The pH electrode has a typical lifespan of 6 months and should be replaced as needed.*

### Technical Specifications
1. pH Measurement Range: 2.00 to 12.00 pH
2. pH Accuracy: ±0.10 pH units within ±10°C of calibration temperature
3. Temperature Range: -2°C to 50°C
4. Temperature Accuracy: ±0.2°C
5. Memory Capacity: 43,300 measurements
6. Battery Life:
    A. 1 year with Bluetooth Always On
    B. 2 years with Bluetooth Off Water Detect
    C. 3 years with Bluetooth Always Off
7. Dimensions: 22.86 x 4.27 cm
8. Weight: 268.2 mg

### Replacing the Electrode (Needs to be done every 6 months) 
1. [MX2500 Replacement Electrode](https://www.onsetcomp.com/products/accessories/mx2500-electrode#compatible-items)
    Cheaper to do a purchase order on LI-COR INC (approved vendor) than VWR 

2. [MX2500 Anti-Biofouling Copper Guard](https://www.onsetcomp.com/products/accessories/mx2500-guard)
    Cheaper to do a purchase order on LI-COR INC (approved vendor) than VWR  
