# Shopify React

A data controller for Shopify Storefront data.

## Initialization

To use the Shopify React plugin, start by wrapping your app in the `<CartProvider />`. This provider requires a buy SDK `client`.

```tsx
import { CartProvider, Client } from '@tylermcrobert/shopify-react'

const client = Client.buildClient({
  domain: 'my-store.myshopify.com',
  accessToken: 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx',
})

const App = ({ children }) => (
  <CartProvider client={client}>
    <Cart />
    {children}
  </CartProvider>
)
```

# Using the Cart

use the `useCart` hook to access cart data and state-altering cart methods.

```tsx
import { useCart } from '@tylermcrobert/shopify-react'

const Cart = ({ children }) => {
  const {
    addToCart,
    cartFetchError,
    closeCart,
    errorAdding,
    isCartOpen,
    isLoading,
    openCart,
    shopifyCheckout,
    updateLineItem,
  } = useCart()
  return <div>Subtotal: ${shopifyCheckout.subtotalPrice}</div>
}
```
