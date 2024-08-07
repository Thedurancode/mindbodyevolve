# MyPCPHealth WooCommerce Integration

## Description

This plugin integrates WooCommerce with the MyPCPHealth API to manage patient information, prescriptions, and fills directly from WooCommerce orders. 

## Features

- Create patients in MyPCPHealth when a WooCommerce order is placed.
- Update patient information when customer details are updated.
- Create prescriptions and fills in MyPCPHealth based on WooCommerce orders.
- Cancel prescriptions in MyPCPHealth when WooCommerce orders are canceled.
- Custom checkout field for capturing the patient's birth date.
- Admin dashboard to view prescription status.

## Installation

1. Upload the `mypcphealth-woocommerce` folder to the `/wp-content/plugins/` directory.
2. Activate the plugin through the 'Plugins' menu in WordPress.
3. Go to the MyPCPHealth settings page (`MyPCPHealth -> Settings`) and enter your API credentials.

## Usage

1. **Add Custom Checkout Field:**
   - The plugin adds a custom checkout field for the birth date. This information is sent to MyPCPHealth when creating a patient.

2. **Order Handling:**
   - When an order is placed, the plugin creates a patient, a prescription, and a fill in MyPCPHealth.
   - If an order is canceled, the corresponding prescription in MyPCPHealth is also canceled.

3. **Admin Dashboard:**
   - The plugin adds a custom admin dashboard to view the status of prescriptions.

## Hooks and Actions

- `woocommerce_after_order_notes`: Adds the custom checkout field.
- `woocommerce_checkout_update_order_meta`: Saves the custom checkout field data.
- `woocommerce_thankyou`: Handles order creation to integrate with MyPCPHealth.
- `profile_update`: Updates patient information when customer details are updated.
- `woocommerce_order_status_cancelled`: Cancels prescriptions in MyPCPHealth when WooCommerce orders are canceled.

## API Functions

### Headers

```php
function mypcphealth_get_headers() {
    return [
        'account-id' => get_option('​⬤