import { useState } from "react";

export default function FuturesProfitCalculator() { const [margin, setMargin] = useState(0); const [leverage, setLeverage] = useState(1); const [priceChange, setPriceChange] = useState(0);

const profit = margin * leverage * (priceChange / 100); const total = margin + profit;

return ( <div className="max-w-md mx-auto p-4 bg-white rounded-2xl shadow-md space-y-4"> <h1 className="text-xl font-bold text-center">Futures Profit Calculator</h1>

<div className="space-y-2">
    <label className="block text-sm font-medium">Margin ($)</label>
    <input
      type="number"
      value={margin}
      onChange={(e) => setMargin(parseFloat(e.target.value) || 0)}
      className="w-full p-2 border rounded-xl"
    />
  </div>

  <div className="space-y-2">
    <label className="block text-sm font-medium">Leverage (×)</label>
    <input
      type="number"
      value={leverage}
      onChange={(e) => setLeverage(parseFloat(e.target.value) || 1)}
      className="w-full p-2 border rounded-xl"
    />
  </div>

  <div className="space-y-2">
    <label className="block text-sm font-medium">Price Change (%)</label>
    <input
      type="number"
      value={priceChange}
      onChange={(e) => setPriceChange(parseFloat(e.target.value) || 0)}
      className="w-full p-2 border rounded-xl"
    />
  </div>

  <div className="p-4 bg-gray-50 rounded-xl">
    <p className="text-sm">Profit/Loss: <span className="font-bold">${profit.toFixed(2)}</span></p>
    <p className="text-sm">Final Total: <span className="font-bold">${total.toFixed(2)}</span></p>
  </div>
</div>

); }
