# Dhanorkar Mobile Shop — GitHub Pages + Firebase

This is a Flipkart-inspired starter storefront for Dhanorkar Mobile Shop, Bhokar.
It includes product search/filter, New/Used categories, cart, WhatsApp enquiry/order,
Firebase email/password admin login, Firestore product data, and Firebase Storage photos.

## 1. Create Firebase project
1. Open https://console.firebase.google.com/ and create a project.
2. Add a Web App in Project settings.
3. Copy the Firebase config into `index.html` where it says `PASTE_API_KEY`, etc.
4. In Firebase Authentication > Sign-in method, enable **Email/Password**.
5. In Authentication > Users, add your admin email and password manually.
   Do not add a public sign-up form.

## 2. Enable database and image storage
1. Create a Firestore Database (start in production mode).
2. Create a Storage bucket.
3. In Firestore Rules, paste `firestore.rules` from this project.
4. In Storage Rules, paste `storage.rules` from this project.
5. In BOTH rules files, replace `ADMIN_EMAIL_HERE` with the exact admin email
   you created in Firebase Authentication.
6. Publish the rules.

The rules allow anyone to read product listings, but only the signed-in admin email
can add/edit/delete products and upload product images.

## 3. Publish on GitHub Pages
1. Create a GitHub repository, e.g. `dhanorkar-mobile-shop`.
2. Upload `index.html` to the repository root.
3. Commit the changes.
4. Open repository Settings > Pages.
5. Under Build and deployment choose Deploy from a branch.
6. Select `main` and `/ (root)`, then Save.
7. Wait for the published GitHub Pages URL.

## 4. Use the website
- Open the public GitHub Pages URL to see the shop.
- Tap **Admin Login**, sign in with the admin email/password.
- Fill Brand, Model, Price, RAM, Storage, New/Used, stock and select multiple photos.
- Tap Save Product. Products appear on the public website automatically.
- To change a product, tap Edit in Admin Panel. To mark sold, set Stock to Sold.
- Customers can add phones to cart and send the full order details to WhatsApp.

## Important
- WhatsApp order destination is set in `index.html` as `SHOP_WHATSAPP = "919922338230"`.
  This is the shop number previously supplied. Change it if needed (country code, no +).
- The WhatsApp flow opens a pre-filled message; the customer must press Send in WhatsApp.
- GitHub Pages hosts the frontend only. Firebase handles login, database and image storage.
- Firebase Storage may require a billing plan depending on current Firebase project/bucket
  eligibility and usage. Check Firebase Console billing/usage before uploading many images.
- Do not publish your Firebase service-account key. This project only uses web-app config;
  secure access is controlled by Firebase Rules.
