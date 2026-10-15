# Green Gallery app

On-call terrace and balcony garden care app. Customers browse services, book a visit, and call or WhatsApp the team. Staff get a PIN-protected screen to manage bookings.

## 1. Edit your details first

Open `www/index.html` and change the `CONFIG` block near the top of the script:

- `phone`: number for the Call button, with country code
- `whatsapp`: WhatsApp number, digits only, with country code
- `staffPin`: PIN for staff mode (default `1234`, change it)

Services and time slots are in the same file (`SERVICES`, `visitSlots`).

## 2. Get the APK (no Android Studio needed)

1. Create a free GitHub account and a new repository.
2. Upload everything in this folder, including the hidden `.github` folder.
3. Open the repository's **Actions** tab and run **Build Android APK** (it also runs on every push).
4. When it finishes (about 5 to 8 minutes), open the run and download the **green-gallery-apk** artifact. Unzip it to get `app-debug.apk`.
5. Copy the APK to an Android phone and install it. Allow "install from unknown sources" when asked.

## How it works

- Staff mode: on the Home screen tap **Staff login** at the bottom and enter the PIN. A **Staff** tab appears with booking status updates, call and WhatsApp buttons.
- Booking data is stored on the phone only. After submitting, the app offers to send the request to your WhatsApp number, which is how bookings reach you. The Staff tab shows only bookings made on the same phone.

## Limits of this first version

- Debug APK: fine for sharing and testing, not for Play Store upload. A signed release build is needed for that.
- No shared backend, logins or push notifications. Adding Firebase would give real shared bookings across customer and staff phones.
- Monthly and AMC plans are not included yet, as requested.
