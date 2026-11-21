<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Bigasan POS</title>
  <style>
    body {
      max-width: 900px;
      margin: 30px auto;
      padding: 0 16px;
      font-family: Arial, sans-serif;
      color: #222;
    }
    h1 { color: #236b3b; }
    .layout { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; }
    section { border: 1px solid #ddd; border-radius: 8px; padding: 16px; }
    label { display: block; margin-top: 12px; }
    input, select, button {
      box-sizing: border-box;
      width: 100%;
      padding: 10px;
      margin-top: 5px;
    }
    button {
      border: 0;
      border-radius: 5px;
      background: #236b3b;
      color: white;
      cursor: pointer;
    }
    button:hover { background: #194f2b; }
    .remove { width: auto; padding: 5px 9px; background: #b3261e; }
    table { width: 100%; border-collapse: collapse; margin-top: 12px; }
    th, td { padding: 8px 4px; border-bottom: 1px solid #ddd; text-align: left; }
    .total { font-size: 1.3rem; font-weight: bold; text-align: right; }
    #receipt {
      width: 100%;
      min-height: 120px;
      box-sizing: border-box;
      margin-top: 10px;
      padding: 10px;
      white-space: pre-wrap;
    }
    @media (max-width: 650px) {
      .layout { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>
  <h1>Bigasan POS</h1>
  <p>Rice sales and inventory tracker</p>

  <div class="layout">
    <section>
      <h2>Inventory</h2>
      <table>
        <thead>
          <tr><th>Rice</th><th>Price/kg</th><th>Stock (kg)</th></tr>
        </thead>
        <tbody id="inventory"></tbody>
      </table>
    </section>

    <section>
      <h2>New Sale</h2>
      <label for="rice">Rice variety</label>
      <select id="rice"></select>

      <label for="quantity">Quantity (kg)</label>
      <input id="quantity" type="number" min="0.1" step="0.1" value="1" />

      <button id="addButton">Add to cart</button>

      <h3>Cart</h3>
      <table>
        <thead>
          <tr><th>Item</th><th>Qty</th><th>Subtotal</th><th></th></tr>
        </thead>
        <tbody id="cart"></tbody>
      </table>

      <p class="total">Total: ₱<span id="total">0.00</span></p>
      <button id="checkoutButton">Complete sale</button>

      <h3>Last receipt</h3>
      <textarea id="receipt" readonly placeholder="Your receipt will appear here."></textarea>
    </section>
  </div>

  <script>
    const defaultProducts = [
      { id: 1, name: "Sinandomeng", price: 52, stock: 100 },
      { id: 2, name: "Jasmine", price: 58, stock: 80 },
      { id: 3, name: "Dinorado", price: 60, stock: 60 }
    ];

    let products = JSON.parse](#)
