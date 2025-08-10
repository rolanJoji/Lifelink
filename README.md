# LifeLink Cute Tomodachi Edition - Mobile APK Build

## Termux Keystore Creation (on phone)
```bash
pkg update && pkg install openjdk-17 -y
keytool -genkeypair -v -keystore mykeystore.jks -keyalg RSA -keysize 2048 -validity 10000 -alias MyAlias
base64 mykeystore.jks > keystore.b64
cat keystore.b64
```
Add secrets in GitHub:
- `KEYSTORE_B64`
- `KEYSTORE_PASSWORD`
- `KEY_ALIAS`
- `KEY_PASSWORD`

## GitHub Mobile Steps
1. Create new repo & upload project ZIP
2. Add secrets above in Settings → Secrets → Actions
3. Go to Actions tab → Run workflow → Download APK from artifacts

## Notes
- Workflow auto-downloads Godot 4.3 headless + Android export templates
- APK name includes timestamp for uniqueness
