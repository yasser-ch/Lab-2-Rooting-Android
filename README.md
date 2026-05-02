# Lab Rooting Android — Sécurité Mobile

## Description

Laboratoire de sécurité mobile portant sur le rooting Android.
L'objectif est de comprendre ce que le root modifie, comment tracer les changements,
et comment remettre l'environnement à zéro.

---

## Environnement utilisé

| Champ | Valeur |
|---|---|
| Support | AVD — Pixel 6 Pro, API 33 (Google APIs) |
| Version Android | Android 13 (API 33) |
| Application testée | FireStorm (app-debug) v1.0 |
| OS hôte | Windows |
| Outils | Android Studio, ADB, Emulator |

---

## Commandes clés exécutées

```bash
# Lancement de l'AVD en mode writable-system
emulator -avd Pixel_6_Pro_API_33 -writable-system

# Activation du root
adb root

# Remontage en lecture/écriture
adb remount

# Vérifications
adb shell id
adb shell getprop ro.boot.verifiedbootstate
adb shell getprop ro.boot.veritymode

# Sauvegarde des logs
adb logcat -d > logcat_root_check.txt
```

---

## Résultats observés

| Commande | Résultat |
|---|---|
| `adb root` | `restarting adbd as root` |
| `adb shell id` | `uid=0(root) gid=0(root)` |
| `ro.boot.verifiedbootstate` | `orange` |
| `ro.boot.veritymode` | `enforcing` |

---

## Règles du lab

- Application de test et labo uniquement
- Données fictives uniquement
- Rien ne sort du périmètre de test
- Reset AVD obligatoire en fin de séance ✅

---

## Rapport

[Lab_2.pdf](https://github.com/user-attachments/files/27302179/Lab_2.pdf)


---

*Cours : Sécurité des Applications Mobiles*
