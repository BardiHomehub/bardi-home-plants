![MIT License](https://img.shields.io/github/license/BardiHomehub/bardi-home-plants)
![GitHub release](https://img.shields.io/github/v/release/BardiHomehub/bardi-home-plants)
![Last Commit](https://img.shields.io/github/last-commit/BardiHomehub/bardi-home-plants)


# 🌿 Bardi Home – Plant Tracker for Home Assistant

A modular YAML-based system to track watering and fertilizing of your plants in Home Assistant.  
Each plant has its own logic: template sensors, manual buttons, automations, and an optional UI card.

---

## 🛠️ Configuration (configuration.yaml)

```yaml
input_datetime: !include_dir_merge_named inputs/datetime/
input_number: !include_dir_merge_named inputs/number/
input_button: !include_dir_merge_named inputs/button/

template: !include_dir_merge_list templates/
automation: !include_dir_merge_list automations/
```

---

## 📁 Folder Structure

- `inputs/datetime/` → last watering/fertilizing dates  
- `inputs/number/` → watering/fertilizing intervals  
- `inputs/button/` → manual control buttons  
- `templates/` → template sensors (next due, days since)  
- `automations/` → reminders and timestamp actions  
- `ui/` → optional Lovelace popup cards  
- `assets/` → plant images for GitHub preview (optional)

---

## 📦 Required via HACS

- `button-card`  
- `browser_mod`

---

## ➕ How to Add a New Plant

1. Copy all `kalanchoe.yaml` files from each folder  
2. Rename all entities (e.g. replace `kalanchoe` with `lavender`)  
3. Update the plant name and care info in the UI card  
4. Add the UI card to Lovelace

---

## 🖼️ UI Background Images

If you want background images (e.g. `Kalanchoe.jpg`) in your Lovelace UI cards,  
place them in your Home Assistant `/config/www/` folder.

In your YAML use:

```yaml
background-image: url("/local/Kalanchoe.jpg")
```

> `/local/` maps to the `www/` folder in Home Assistant.  
> The `assets/` folder in this repository is only for GitHub preview images.

---

## 📄 License

MIT – free to use and modify.
