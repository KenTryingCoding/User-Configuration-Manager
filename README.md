# ⚙️ Python Settings Manager

A lightweight, case-insensitive CRUD (Create, Read, Update, Delete) utility module written in Python. This script allows you to easily manage user configurations, application preferences, or system settings stored inside a standard Python dictionary.

---

## ✨ Features

* **🛡️ Case Insensitivity:** Automatically normalizes all input keys and values to lowercase to prevent accidental duplicate entries (e.g., treating `Theme` and `theme` as identical).
* **➕ Safe Additions:** Built-in safeguards stop you from accidentally overwriting an existing setting during creation.
* **🔄 Safe Updates:** Restricts configuration updates exclusively to keys that already exist in the system.
* **📋 Formatted View:** Generates a human-readable summary of all active settings with automatically capitalized headers.

---

## 🚀 API Reference

### `add_setting(settings_dict, pair)`

Adds a new key-value tuple to the dictionary.

* **Parameters:** * `settings_dict` *(dict)*: The target configurations dictionary.
* `pair` *(tuple)*: A `(key, value)` pair to insert.


* **Returns:** Success or error message string.

### `update_setting(settings_dict, pair)`

Modifies an existing key's value.

* **Parameters:** * `settings_dict` *(dict)*: The target configurations dictionary.
* `pair` *(tuple)*: A `(key, new_value)` pair.


* **Returns:** Success or error message string.

### `delete_setting(settings_dict, key)`

Removes a configuration profile entirely.

* **Parameters:** * `settings_dict` *(dict)*: The target configurations dictionary.
* `key` *(str)*: The target setting name to drop.


* **Returns:** Confirmation message string.

### `view_settings(settings_dict)`

Outputs a cleanly formatted string block of all active settings.

---

## 💻 Quickstart Example

```python
# Your initial configuration store
test_settings = {
    'theme': 'monospace',
    'notifications': 'disable',
    'volume': 'medium'  
}

# 1. View current settings
print(view_settings(test_settings))
# Output:
# Current User Settings:
# Theme: monospace
# Notifications: disable
# Volume: medium

# 2. Add a new setting safely
print(add_setting(test_settings, ('Font', 'Consolas')))
# Output: Setting 'font' added with value 'consolas' successfully!

# 3. Update an existing setting (Case-Insensitive)
print(update_setting(test_settings, ('NOTIFICATIONS', 'enable')))
# Output: Setting 'notifications' updated to 'enable' successfully!

# 4. Delete a setting
print(delete_setting(test_settings, 'volume'))
# Output: Setting 'volume' deleted successfully!

```
