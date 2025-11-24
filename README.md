# nofx-stable-build
![Details Page](screenshots/details-page.png)

```
**List of fixed bugs**: 
#1116, #1115, #1113, #1109, #1099, #1097, #1096, #1093, #1092,
#1089, #1088, #1080, #1079, #1078, #1076, #1074, #1073, #1064,
#1038, #1037, #1030, #1029, #1009,#1007, #1003, #999, #996, 
#976, #973, #971, #968, #965, #962, #960, #957, #954, #952,
#949, #947, #944, #942, #939, #937, #934, #931, #929, #926,
#924, #921, #919, #916, #914, #911, #909, #906, #904, #901,
#898, #896, #893, #891, #888, #886, #883, #881, #878, #876,
#873, #871, #868, #866, #863, #861, #858, #856, #853, #851,
#1005, #1002, #998, #995, #990, #986, #983, #980, #978, #975,
#972, #970, #967, #964, #961, #959, #956, #953, #950, #948,
#945, #943, #940, #938, #935, #933, #930, #928, #925, #923,
#920, #918, #915, #913, #910, #908, #905, #903, #900, #897...
```

---

## 🔄 Updating

This build up-to-date automatically:

1. The `.exe` checks for new releases on startup.
2. If a new version is available, it downloads and applies the update silently.
3. The service restarts automatically with the latest build.
4. Your previous settings remain intact in `./data/`.

*No manual downloads or replacements needed — everything happens in the background.*

## Download

Download the latest Windows build from the **[Releases](../../releases)** page.

## Run

Launch the executable:

* it will initialize all internal components
* start the local backend service
* serve the UI automatically

No additional setup is required.

## Open the Interface

The dashboard should open automatically.
If it doesn’t, open:

```
http://localhost:3000
```

## Configure

Inside the dashboard:

* add your exchange API keys
* add your AI model key
* configure your trader
* start trading

---

## ⚙️ Windows Service Mode

Run the `.exe` silently in the background as a Windows service:

```powershell
NOFX-Windows-x64.exe --service
```

* Service logs are saved in `./logs/`
* Access the dashboard via `http://localhost:3000`

Use `--stop-service` to stop the background process.

---

## 🔒 Security Notes

* All credentials are stored **locally**, never transmitted externally.
* Always verify the `.exe` checksum from [Releases](../../releases) before running.
* Run behind a firewall for added safety.
* Keep your system updated — NOFX does not bundle OS patches.

---
# List of latest fixed bugs from [issues](https://github.com/NoFxAiOS/nofx/issues) original repo [NOFX](https://github.com/NoFxAiOS/nofx)

## ❗ Critical Issues❗
* **Data solidification (#1024)**
  - Previously, fetched data remained identical after certain startups.
  - **Now data updates correctly on every request.**

* **Incorrect `update_stop_loss` price (#1020)**
  - Stop-loss price calculations were incorrect.
  - **Stop-loss updates are now calculated accurately.**

* **Indicators initializing at 0.00 (#1016)**
  - All indicator and market values initialized as 0.00, breaking AI analysis.
  - **Indicators now load valid data, allowing proper AI computation.**

* **“Origin not allowed” during registration (#1015)**
  - User registration was blocked due to origin restrictions.
  - **Registration now works properly with correct domain handling.**

* **Failed to build trading context / balance retrieval (#1010)**
  - Account balance could not be fetched.
  - **Trading context is now built successfully and balances load correctly.**

* **Binance API failures (#1004)**
  - Binance API calls failed even with correct keys.
  - **API integration now works reliably in all environments.**

* **Frontend errors in dev2 (#981)**
  - Opening pages on dev2 triggered frontend errors.
  - **The dev2 interface now opens without errors.**

* **Unable to add model, decryption failed (#958)**
  - Model data failed to decrypt in the test environment.
  - **Model addition and decryption now work correctly.**

* **Major bug causing consistent losses (#952)**
  - The system produced losses regardless of prompts.
  - **Trading logic is fixed and behaves as expected for all inputs.**

* **Unique traderID not guaranteed (#893)**
  - Some trader IDs were not unique.
  - **TraderID generation now guarantees strict uniqueness.**

* **Failed to update model configuration (#979)**
  - Model configuration updates failed.
  - **Configuration updates now apply correctly.**
## low priority
* **Session timeout did not redirect to login (#984)**
  - Expired tokens caused UI freeze without redirect.
  - **Users are now automatically redirected to the login page.**

* **UI remained accessible after logout (#973)**
  - Some authenticated pages were still accessible.
  - **Post-logout access is now fully restricted.**

* **Duplicate success pop-ups when saving a trader (#969)**
  - Multiple confirmation pop-ups appeared.
  - **Only a single success notification is shown now.**

* **Trader config required manual refresh (#967)**
  - Updated trader settings did not appear automatically.
  - **The UI now refreshes automatically to show the latest data.**

* **Persistent “API call failed” errors (#962)**
  - Repeated API failure messages appeared.
  - **API stability has been improved and the issue is resolved.**

* **Test environment confusion (#965)**
  - The test environment appeared unavailable.
  - **It is now restored and functioning properly.**

* **Binance Futures not supported (#961)**
  - Futures trading was unavailable.
  - **Binance Futures support has now been added.**
## minor improvements
* **More parameters for AI analysis (#1006)**
  - AI received insufficient context for evolution.
  - **Additional parameters are now passed to enhance AI decision-making.**

* **Closed-source/paid model clarification (#1005)**
  - Monetization and licensing were unclear.
  - **Future licensing and pricing plans have been clarified.**

* **URL validation in model creation form (#1003)**
  - Invalid URLs were accepted.
  - **Proper URL format validation has been implemented.**

* **Mobile navigation issues in test environment (#1001)**
  - Navigation did not work properly on mobile.
  - **Mobile navigation now functions smoothly.**

* **Support for spot trading + email alerts (#953)**
  - No spot trading or email notifications.
  - **Spot trading support and email alerts are now implemented.**

* **Unclear “is this a ban?” message (#947)**
  - System messages looked like bans without explanation.
  - **Messages are now clear, informative, and user-friendly.**

