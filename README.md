# रामदेव राजस्थानी फौजी ढाबा — Ramdev Rajasthani Foji Dhaba · QR Menu

Digital QR menu for Ramdev Rajasthani Foji Dhaba, Nipani (Karnataka). Built from the Shree Shivneri Dhaba project, but it is a separate site with its own data.
Plain static site for GitHub Pages: no build step.

- Restaurant details: `data/restaurant.json`
- Menu: `data/menu.json` (95 dishes, 9 categories, from the printed menu)
- Dish photo names: `assets/menu/PHOTO-FILENAMES.txt`
- Editing guide: `docs/CUSTOMER_SETUP.md`

## Differences from Shree Shivneri
- No Zomato/Swiggy strip (`deliveryPartners` is empty)
- Two phone numbers: Call K.R. (8824607707) and Call S.R. (8302295601), in the header and footer (`phone2`, `phone2Label`)
- Rice prices use the printed Half/Full columns (`variations`)
- Hindi names (`contentLang: "hi"`), maroon + yellow colours to match the printed menu
- WhatsApp, Location, Google Review and Instagram buttons switch on automatically once their links are filled in `restaurant.json`

## Dish photos
Every dish points to `assets/menu/<dish-id>.jpg`. Upload photos with the names in `PHOTO-FILENAMES.txt`; until then each card shows a placeholder letter. Landscape 4:3, about 800×600, under 150 KB.

## To confirm with the client
1. **स्पे. राजस्थानी थाली ₹200**: a sticker covers the last word on the printed menu. "थाली" is my guess.
2. **स्पे. हल्दी (सिजनल) ₹180**: the English side says "Sp.Rajasthani (Sijanal)". Which name is correct?
3. **पनीर टिक्का लवाबदार ₹190**: the English side says "Paneer Masala Lavbdar". Which is correct?
4. **कडी तडका ₹110, Veg Kadhai, Veg Jaipuri**: the English side is hidden by glare; the Hindi names and prices are clear.
5. **Veg Pulao / Matar Pulao half price ₹60**: handwritten in blue pen. Confirm it.
6. **Biryani, Hyderabadi Biryani, Dal Khichdi, Marwadi Pulao** show only a Full price. Confirm there is no half.
7. **पनीर मराठा** was printed; I used **पनीर पराठा** (the English side says Paneer Parotha). "स्पे.मावाडी पुलाव" became **स्पे. मारवाडी पुलाव**.
8. English names are spelling-corrected (e.g. "Stean Rice" → Steam Rice, "Plain Non" → Plain Naan, "Cadi Fry" → Kadhi Fry). Hindi names are kept as printed.
9. **Logo**: none supplied. `assets/logo/ramdev-logo.svg` is a simple text placeholder. Replace it with the client's logo (and update `logo` in restaurant.json if the filename differs).
10. **Not provided yet**: WhatsApp number, Google Maps link, address, Google review link + rating, Instagram, opening hours, site URL.

## Test locally
```bash
cd Ramdev-Rajasthani-Foji-Dhaba
python -m http.server 8000
```
Open http://localhost:8000.

## Deploy
Same steps as Shree Shivneri: create a **new** public repository (e.g. `Ramdev-Rajasthani-Foji-Dhaba`), upload these files (including `.nojekyll`), then Settings → Pages → Deploy from branch `main`, folder `/ (root)`. Put the live address in `siteUrl` and make the QR code only after the site opens on mobile data.
