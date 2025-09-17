# BODL to GA4 Ecommerce Tracking Script

A JavaScript solution for tracking BigCommerce ecommerce events using BODL (Big Open Data Layer) and sending them to Google Analytics 4 (GA4) in the proper Enhanced Ecommerce format.

## 🚀 Features

- **Complete Ecommerce Tracking**: Tracks all major ecommerce events (view_item, add_to_cart, purchase, etc.)
- **Duplicate Prevention**: Uses event IDs to prevent duplicate event firing
- **Reliable Data Source**: Uses BigCommerce's BODL instead of DOM scraping
- **Proper GA4 Format**: Maps BODL data to GA4's Enhanced Ecommerce structure

## 📋 Prerequisites

- **BigCommerce Store** with BODL enabled
- **Stencil Theme** (required for BODL functionality)
- **Google Analytics 4** property set up

### Enabling BODL on BigCommerce

BODL must be enabled on your BigCommerce store:
- **Via Control Panel**: Go to Advanced Settings > Web Analytics > Enable "Data Layer for developers"

## 🛠 Installation

### BigCommerce Script Manager

1. Go to **Storefront** > **Script Manager** in your BigCommerce admin
2. Click **Create a Script**
3. Configure:
   - **Name**: "BODL to GA4 Tracking"
   - **Location**: Head
   - **Select pages**: All pages
   - **Script category**: Essential
4. Paste the script code in the **HTML** field
5. Save and activate

## 📊 Events Tracked

| BODL Event | GA4 Event | Description |
|------------|-----------|-------------|
| `bodlEvents.product.searchPerformed` | `bodl_search` | Product search performed |
| `bodlEvents.product.categoryViewed` | `bodl_view_item_list` | Category page viewed |
| `bodlEvents.product.pageViewed` | `bodl_view_item` | Product page viewed |
| `bodlEvents.cart.addItem` | `bodl_add_to_cart` | Product added to cart |
| `bodlEvents.cart.viewed` | `bodl_view_cart` | Cart page viewed |
| `bodlEvents.cart.removeItem` | `bodl_remove_from_cart` | Product removed from cart |
| `bodlEvents.checkout.checkoutBegin` | `bodl_begin_checkout` | Checkout process started |
| `bodlEvents.checkout.shippingDetailsProvided` | `bodl_add_shipping_info` | Shipping info added |
| `bodlEvents.checkout.paymentDetailsProvided` | `bodl_add_payment_info` | Payment info added |
| `bodlEvents.checkout.orderPurchased` | `bodl_purchase` | Order completed |

## 📚 Official Documentation

- **BigCommerce BODL Documentation**: [Big Open Data Layer for Storefront Analytics](https://developer.bigcommerce.com/docs/integrations/hosted-analytics)
- **GA4 Enhanced Ecommerce**: [Google Analytics 4 Ecommerce Events](https://developers.google.com/analytics/devguides/collection/ga4/ecommerce)pt instances on the same page

### Debug Mode

Add this line after the script loads to see all events:

```javascript
window.addEventListener('load', function() {
  console.log('BODL Events:', window.bodlEvents);
});
```

## 📚 Official Documentation

- **BigCommerce BODL Documentation**: [Big Open Data Layer for Storefront Analytics](https://developer.bigcommerce.com/docs/integrations/hosted-analytics)
- **GA4 Enhanced Ecommerce**: [Google Analytics 4 Ecommerce Events](https://developers.google.com/analytics/devguides/collection/ga4/ecommerce)
- **BigCommerce Scripts API**: [Scripts API Reference](https://developer.bigcommerce.com/docs/rest-management/scripts)
