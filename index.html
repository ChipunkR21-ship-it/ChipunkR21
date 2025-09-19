// E-Commerce Starter (single-file React component)
// Usage:
// 1) Create a React app (Vite or Create React App).
// 2) Install Tailwind CSS and configure per Tailwind docs.
// 3) Drop this file as `App.jsx` (or paste into your main component).
// 4) This is a self-contained demo: product list, search, filters, cart, checkout mock.

import React, { useEffect, useState } from 'react';

// Sample product data (replace with API calls in real app)
const SAMPLE_PRODUCTS = [
  { id: 1, title: 'Sepatu Lari AeroX', price: 799000, category: 'Sepatu', stock: 12, img: 'https://via.placeholder.com/320x240?text=Sepatu+AeroX' },
  { id: 2, title: 'Kaos Olahraga DryFit', price: 129000, category: 'Pakaian', stock: 34, img: 'https://via.placeholder.com/320x240?text=Kaos+DryFit' },
  { id: 3, title: 'Tas Ransel Urban 20L', price: 249000, category: 'Aksesoris', stock: 8, img: 'https://via.placeholder.com/320x240?text=Ransel+Urban' },
  { id: 4, title: 'Jam Tangan SmartWatch', price: 1599000, category: 'Gadget', stock: 5, img: 'https://via.placeholder.com/320x240?text=SmartWatch' },
  { id: 5, title: 'Kacamata Renang Pro', price: 89000, category: 'Aksesoris', stock: 15, img: 'https://via.placeholder.com/320x240?text=Kacamata+Renang' },
  { id: 6, title: 'Jaket Windbreaker', price: 399000, category: 'Pakaian', stock: 7, img: 'https://via.placeholder.com/320x240?text=Jaket+Windbreaker' }
];

// Utility formatter for currency (Indonesian Rupiah)
const formatRupiah = (value) => {
  return new Intl.NumberFormat('id-ID', { style: 'currency', currency: 'IDR' }).format(value);
};

export default function App() {
  // products state: in real app, fetch from API
  const [products] = useState(SAMPLE_PRODUCTS);

  // UI state
  const [query, setQuery] = useState('');
  const [category, setCategory] = useState('Semua');
  const [sortBy, setSortBy] = useState('popular');
  const [cart, setCart] = useState(() => {
    try {
      const raw = localStorage.getItem('demo_cart');
      return raw ? JSON.parse(raw) : {};
    } catch (e) {
      return {};
    }
  });
  const [isCartOpen, setIsCartOpen] = useState(false);
  const [checkoutOpen, setCheckoutOpen] = useState(false);
  const [selectedProduct, setSelectedProduct] = useState(null);

  useEffect(() => {
    localStorage.setItem('demo_cart', JSON.stringify(cart));
  }, [cart]);

  // Derived lists
  const categories = ['Semua', ...Array.from(new Set(products.map(p => p.category)))];

  function matchesFilter(p) {
    const q = query.trim().toLowerCase();
    if (category !== 'Semua' && p.category !== category) return false;
    if (q && !(`${p.title} ${p.category}`.toLowerCase().includes(q))) return false;
    return true;
  }

  function sortProducts(list) {
    switch (sortBy) {
      case 'price_asc':
        return list.slice().sort((a,b) => a.price - b.price);
      case 'price_desc':
        return list.slice().sort((a,b) => b.price - a.price);
      case 'stock':
        return list.slice().sort((a,b) => b.stock - a.stock);
      default:
        return list; // default (popular)
    }
  }

  const visibleProducts = sortProducts(products.filter(matchesFilter));

  // Cart helpers
  const cartItems = Object.values(cart);
  const cartCount = cartItems.reduce((s, it) => s + it.qty, 0);
  const cartTotal = cartItems.reduce((s, it) => s + it.qty * it.price, 0);

  function addToCart(product, qty = 1) {
    setCart(prev => {
      const existing = prev[product.id];
      const newQty = existing ? existing.qty + qty : qty;
      return { ...prev, [product.id]: { ...product, qty: Math.min(newQty, product.stock) } };
    });
    setIsCartOpen(true);
  }

  function updateQty(productId, qty) {
    setCart(prev => {
      const copy = { ...prev };
      if (!copy[productId]) return prev;
      if (qty <= 0) delete copy[productId];
      else copy[productId].qty = Math.min(qty, copy[productId].stock);
      return copy;
    });
  }

  function clearCart() {
    setCart({});
  }

  function handleCheckout(details) {
    // Mock processing - in a real app you would call API
    console.log('Checkout details', details, cart);
    // Simulate success: clear cart and close checkout
    clearCart();
    setCheckoutOpen(false);
    alert('Pesanan Anda berhasil dikirim (demo). Terima kasih!');
  }

  return (
    <div className="min-h-screen bg-gray-50">
      <header className="bg-white shadow-sm sticky top-0 z-30">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between items-center h-16">
            <div className="flex items-center gap-4">
              <a href="#" className="text-2xl font-bold text-indigo-600">TokoKu</a>
              <div className="hidden md:flex items-center gap-2">
                <input
                  value={query}
                  onChange={(e) => setQuery(e.target.value)}
                  placeholder="Cari produk..."
                  className="border rounded-md px-3 py-2 outline-none w-64"
                />
                <select value={category} onChange={(e) => setCategory(e.target.value)} className="border rounded-md px-2 py-2">
                  {categories.map(c => <option key={c} value={c}>{c}</option>)}
                </select>
                <select value={sortBy} onChange={(e) => setSortBy(e.target.value)} className="border rounded-md px-2 py-2">
                  <option value="popular">Populer</option>
                  <option value="price_asc">Harga: Rendah &uarr;</option>
                  <option value="price_desc">Harga: Tinggi &darr;</option>
                  <option value="stock">Stok: Banyak</option>
                </select>
              </div>
            </div>

            <div className="flex items-center gap-4">
              <nav className="hidden sm:flex gap-4 items-center">
                <a href="#" className="text-sm text-gray-600 hover:text-gray-900">Tentang</a>
                <a href="#" className="text-sm text-gray-600 hover:text-gray-900">Bantuan</a>
              </nav>

              <button onClick={() => setIsCartOpen(true)} className="relative inline-flex items-center px-3 py-2 rounded-md bg-indigo-600 text-white">
                <svg xmlns="http://www.w3.org/2000/svg" className="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M3 3h2l1 5h13l1-5h2" />
                </svg>
                Keranjang
                {cartCount > 0 && (
                  <span className="ml-2 inline-flex items-center justify-center px-2 py-1 text-xs font-bold leading-none text-indigo-800 bg-indigo-200 rounded-full">{cartCount}</span>
                )}
              </button>
            </div>
          </div>
        </div>
      </header>

      <main className="py-8">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="grid grid-cols-1 lg:grid-cols-4 gap-6">
            {/* Filters column */}
            <aside className="lg:col-span-1 bg-white p-4 rounded-lg shadow-sm">
              <h3 className="font-semibold mb-3">Filter</h3>
              <div className="mb-4">
                <label className="block text-sm text-gray-600">Kategori</label>
                <select value={category} onChange={(e) => setCategory(e.target.value)} className="w-full border rounded-md mt-2 px-2 py-2">
                  {categories.map(c => <option key={c} value={c}>{c}</option>)}
                </select>
              </div>

              <div className="mb-4">
                <label className="block text-sm text-gray-600">Sortir</label>
                <select value={sortBy} onChange={(e) => setSortBy(e.target.value)} className="w-full border rounded-md mt-2 px-2 py-2">
                  <option value="popular">Populer</option>
                  <option value="price_asc">Harga: Rendah</option>
                  <option value="price_desc">Harga: Tinggi</option>
                </select>
              </div>

              <div>
                <h4 className="font-medium">Kategori Cepat</h4>
                <div className="mt-2 flex flex-wrap gap-2">
                  {categories.slice(1).map(c => (
                    <button key={c} onClick={() => setCategory(c)} className={`text-sm px-3 py-1 rounded-full border ${category===c ? 'bg-indigo-50' : ''}`}>{c}</button>
                  ))}
                </div>
              </div>
            </aside>

            {/* Products grid */}
            <section className="lg:col-span-3">
              <div className="mb-4 flex items-center justify-between">
                <h2 className="text-xl font-bold">Produk</h2>
                <div className="block md:hidden">
                  <input
                    value={query}
                    onChange={(e) => setQuery(e.target.value)}
                    placeholder="Cari produk..."
                    className="border rounded-md px-3 py-2 w-48"
                  />
                </div>
              </div>

              {visibleProducts.length === 0 ? (
                <div className="bg-white p-8 rounded-lg shadow-sm text-center">Tidak ada produk yang cocok.</div>
              ) : (
                <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                  {visibleProducts.map(p => (
                    <article key={p.id} className="bg-white rounded-lg shadow-sm overflow-hidden flex flex-col">
                      <img src={p.img} alt={p.title} className="w-full h-44 object-cover" />
                      <div className="p-4 flex-1 flex flex-col">
                        <h3 className="font-semibold text-lg">{p.title}</h3>
                        <p className="text-sm text-gray-500 mt-1">{p.category} • Stok: {p.stock}</p>
                        <div className="mt-3 flex items-center justify-between">
                          <div className="text-lg font-bold">{formatRupiah(p.price)}</div>
                          <div className="flex gap-2">
                            <button onClick={() => setSelectedProduct(p)} className="text-sm px-3 py-1 border rounded-md">Detail</button>
                            <button onClick={() => addToCart(p)} className="text-sm px-3 py-1 bg-indigo-600 text-white rounded-md">Tambah</button>
                          </div>
                        </div>
                      </div>
                    </article>
                  ))}
                </div>
              )}
            </section>
          </div>
        </div>
      </main>

      {/* Footer */}
      <footer className="bg-white border-t mt-8">
        <div className="max-w-7xl mx-auto px-4 py-6 text-sm text-gray-600">© {new Date().getFullYear()} TokoKu. Semua hak dilindungi.</div>
      </footer>

      {/* Cart drawer */}
      {isCartOpen && (
        <div className="fixed inset-0 z-40">
          <div className="absolute inset-0 bg-black/30" onClick={() => setIsCartOpen(false)} />
          <div className="absolute right-0 top-0 h-full w-full sm:w-96 bg-white shadow-lg p-4 overflow-y-auto">
            <div className="flex justify-between items-center mb-4">
              <h3 className="text-lg font-semibold">Keranjang</h3>
              <div className="flex items-center gap-2">
                <button onClick={clearCart} className="text-sm text-red-600">Kosongkan</button>
                <button onClick={() => setIsCartOpen(false)} className="px-3 py-1 border rounded-md">Tutup</button>
              </div>
            </div>

            {cartItems.length === 0 ? (
              <div className="text-gray-500">Keranjang kosong.</div>
            ) : (
              <div className="space-y-4">
                {cartItems.map(item => (
                  <div key={item.id} className="flex items-center gap-3">
                    <img src={item.img} alt={item.title} className="w-16 h-16 object-cover rounded" />
                    <div className="flex-1">
                      <div className="font-medium">{item.title}</div>
                      <div className="text-sm text-gray-500">{formatRupiah(item.price)} • Stok {item.stock}</div>
                      <div className="mt-2 flex items-center gap-2">
                        <button onClick={() => updateQty(item.id, item.qty-1)} className="px-2 py-1 border rounded">-</button>
                        <div className="px-3 py-1 border rounded">{item.qty}</div>
                        <button onClick={() => updateQty(item.id, item.qty+1)} className="px-2 py-1 border rounded">+</button>
                      </div>
                    </div>
                    <div className="text-right">
                      <div className="font-semibold">{formatRupiah(item.price * item.qty)}</div>
                      <button onClick={() => updateQty(item.id, 0)} className="text-sm text-red-600 mt-2">Hapus</button>
                    </div>
                  </div>
                ))}

                <div className="border-t pt-4">
                  <div className="flex justify-between items-center">
                    <div className="text-sm text-gray-600">Total</div>
                    <div className="text-lg font-bold">{formatRupiah(cartTotal)}</div>
                  </div>
                  <div className="mt-4 flex gap-2">
                    <button onClick={() => { setCheckoutOpen(true); setIsCartOpen(false); }} className="flex-1 px-4 py-2 bg-green-600 text-white rounded-md">Checkout</button>
                    <button onClick={() => setIsCartOpen(false)} className="px-4 py-2 border rounded-md">Lanjut Belanja</button>
                  </div>
                </div>
              </div>
            )}
          </div>
        </div>
      )}

      {/* Checkout modal */}
      {checkoutOpen && (
        <CheckoutModal onClose={() => setCheckoutOpen(false)} onSubmit={handleCheckout} total={cartTotal} />
      )}

      {/* Product detail modal */}
      {selectedProduct && (
        <ProductModal product={selectedProduct} onClose={() => setSelectedProduct(null)} onAdd={addToCart} />
      )}
    </div>
  );
}

function ProductModal({ product, onClose, onAdd }) {
  const [qty, setQty] = useState(1);
  useEffect(() => setQty(1), [product]);

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center">
      <div className="absolute inset-0 bg-black/30" onClick={onClose} />
      <div className="bg-white rounded-lg p-6 z-10 max-w-3xl w-full shadow-lg">
        <div className="flex gap-6">
          <img src={product.img} alt={product.title} className="w-48 h-48 object-cover rounded" />
          <div className="flex-1">
            <h3 className="text-2xl font-semibold">{product.title}</h3>
            <div className="text-gray-500 mt-1">{product.category}</div>
            <div className="text-2xl font-bold mt-4">{formatRupiah(product.price)}</div>
            <p className="mt-4 text-gray-700">Deskripsi singkat produk. Ganti dengan konten nyata dari backend/produk.</p>

            <div className="mt-4 flex items-center gap-3">
              <label className="text-sm">Jumlah</label>
              <div className="flex items-center gap-2">
                <button onClick={() => setQty(q => Math.max(1, q-1))} className="px-2 py-1 border rounded">-</button>
                <input value={qty} onChange={(e) => setQty(Math.max(1, Number(e.target.value||1)))} className="w-16 text-center border rounded px-2 py-1" />
                <button onClick={() => setQty(q => Math.min(product.stock, q+1))} className="px-2 py-1 border rounded">+</button>
              </div>
              <div className="text-sm text-gray-500">Stok: {product.stock}</div>
            </div>

            <div className="mt-6 flex gap-2">
              <button onClick={() => { onAdd(product, qty); onClose(); }} className="px-4 py-2 bg-indigo-600 text-white rounded-md">Tambah ke Keranjang</button>
              <button onClick={onClose} className="px-4 py-2 border rounded-md">Tutup</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  );
}

function CheckoutModal({ onClose, onSubmit, total }) {
  const [form, setForm] = useState({ name: '', phone: '', address: '', shipping: 'JNE', note: '' });

  function updateField(k, v) { setForm(f => ({ ...f, [k]: v })); }

  function handleSubmit(e) {
    e.preventDefault();
    if (!form.name || !form.phone || !form.address) {
      alert('Mohon isi nama, nomor telepon, dan alamat pengiriman.');
      return;
    }
    onSubmit(form);
  }

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center">
      <div className="absolute inset-0 bg-black/30" onClick={onClose} />
      <form onSubmit={handleSubmit} className="bg-white rounded-lg p-6 z-10 max-w-2xl w-full shadow-lg">
        <h3 className="text-xl font-semibold mb-4">Checkout</h3>
        <div className="grid grid-cols-1 gap-3">
          <input value={form.name} onChange={(e) => updateField('name', e.target.value)} placeholder="Nama penerima" className="border rounded px-3 py-2" />
          <input value={form.phone} onChange={(e) => updateField('phone', e.target.value)} placeholder="Nomor telepon" className="border rounded px-3 py-2" />
          <textarea value={form.address} onChange={(e) => updateField('address', e.target.value)} placeholder="Alamat lengkap" className="border rounded px-3 py-2" rows={3} />
          <select value={form.shipping} onChange={(e) => updateField('shipping', e.target.value)} className="border rounded px-3 py-2">
            <option>JNE</option>
            <option>J&T</option>
            <option>POS</option>
          </select>
          <input value={form.note} onChange={(e) => updateField('note', e.target.value)} placeholder="Catatan (opsional)" className="border rounded px-3 py-2" />

          <div className="flex justify-between items-center mt-2">
            <div>
              <div className="text-sm text-gray-500">Total pesanan</div>
              <div className="text-lg font-bold">{formatRupiah(total)}</div>
            </div>
            <div className="flex gap-2">
              <button type="button" onClick={onClose} className="px-4 py-2 border rounded-md">Batal</button>
              <button type="submit" className="px-4 py-2 bg-green-600 text-white rounded-md">Bayar</button>
            </div>
          </div>
        </div>
      </form>
    </div>
  );
}

// End of file
