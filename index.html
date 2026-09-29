<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fixie Computer Ventures - Online Order Portal</title>
    
    <!-- OpenStreetMap Leaflet Library CSS -->
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
    <link rel="stylesheet" href="stm.css">
</head>
<body>

    <!-- MAIN ONLINE ORDERS & TRACKING PORTAL -->
    <div class="container">
        <div class="top-nav">
            <div class="brand-container">
                <img src="FCV-Logo.jpg" alt="Fixie Computer Ventures Logo" class="brand-logo" onerror="this.onerror=null; this.src='https://via.placeholder.com/80?text=Fixie+Logo';">
                <h1>Fixie Computer Ventures</h1>
            </div>
            <span class="online-badge"><span class="online-dot"></span> Online System</span>
        </div>

        <div class="orders-hub">
            <div class="orders-header">Your orders</div>
            
            <!-- Clickable Status Tabs -->
            <div class="status-bar">
                <span class="status-item active" onclick="switchTab('all', this)">All</span>
                <span class="status-item" onclick="switchTab('topay', this)">To pay</span>
                <span class="status-item" onclick="switchTab('toship', this)">To ship</span>
                <span class="status-item" onclick="switchTab('toreceive', this)">To receive</span>
                <span class="status-item" onclick="switchTab('toreview', this)">To review</span>
                <span class="status-item" onclick="switchTab('returns', this)">Returns</span>
            </div>

            <!-- Shortcuts -->
            <div class="shortcut-bar">
                <span class="shortcut-item" onclick="openShortcut('cart', this)">🛒 Cart</span>
                <span class="shortcut-item" onclick="openShortcut('address', this)">📍 Address</span>
                <span class="shortcut-item" onclick="openShortcut('payment', this)">💳 Payment methods</span>
            </div>

            <!-- Dynamic Interactive Content Area -->
            <div id="tabContent" class="tab-content-box">
                <!-- Injected via JavaScript -->
            </div>
        </div>
    </div>

    <!-- Image Zoom Lightbox Overlay -->
    <div id="imageZoomModal" class="image-zoom-modal" onclick="closeImageZoom()">
        <span class="zoom-modal-close">&times;</span>
        <img id="zoomedImg" class="zoom-modal-content" src="" alt="Zoomed Item View">
        <div id="zoomedCaption" class="zoom-modal-caption"></div>
    </div>

    <!-- Leaflet JS Library for Real Philippines Map -->
    <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

    <script>
        // Catalog Store Array (10 Items)
        let fixieCatalog = [
            { id: 1, name: "Kingston Fury Beast 16GB DDR4 3200MHz", price: 2450.00, image: "https://images.unsplash.com/photo-1562976540-1502c2145186?auto=format&fit=crop&w=300&q=80" },
            { id: 2, name: "Kingston NV2 1TB NVMe M.2 SSD", price: 3850.00, image: "https://images.unsplash.com/photo-1597872200969-2b65d56bd16b?auto=format&fit=crop&w=300&q=80" },
            { id: 3, name: "Gigabyte GeForce RTX 4060 Eagle OC 8GB", price: 19500.00, image: "https://images.unsplash.com/photo-1587202372775-e229f172b9d7?auto=format&fit=crop&w=300&q=80" },
            { id: 4, name: "AMD Ryzen 5 5600 Desktop Processor", price: 7200.00, image: "https://images.unsplash.com/photo-1555680202-c86f0e12f086?auto=format&fit=crop&w=300&q=80" },
            { id: 5, name: "Gigabyte B550M DS3H AC Motherboard", price: 6100.00, image: "https://images.unsplash.com/photo-1518770660439-4636190af475?auto=format&fit=crop&w=300&q=80" },
            { id: 6, name: "Corsair CV650 650W 80+ Bronze Power Supply", price: 3450.00, image: "https://images.unsplash.com/photo-1587202372634-32705e3bf49c?auto=format&fit=crop&w=300&q=80" },
            { id: 7, name: "Logitech G304 Lightspeed Wireless Mouse", price: 1850.00, image: "https://images.unsplash.com/photo-1615663245857-ac93bb7c39e7?auto=format&fit=crop&w=300&q=80" },
            { id: 8, name: "Rakk Samar Gaming Mechanical Keyboard", price: 1250.00, image: "https://images.unsplash.com/photo-1587829741301-dc798b83add3?auto=format&fit=crop&w=300&q=80" },
            { id: 9, name: "DarkFlash DLM21 Mesh Micro-ATX Case", price: 2100.00, image: "https://images.unsplash.com/photo-1587202372775-e229f172b9d7?auto=format&fit=crop&w=300&q=80" },
            { id: 10, name: "Budget Mid-Range Gaming PC Package", price: 28500.00, image: "https://images.unsplash.com/photo-1587202372616-b43abea06c2a?auto=format&fit=crop&w=300&q=80" }
        ];

        let cartItems = [];
        let activeOrders = [];
        let returnRequests = [];
        let reviewsSubmitted = [];
        let selectedStarRating = 0;
        let selectedPaymentMethod = "GCash";
        let savedCardDetails = null;

        let savedAddresses = [
            { name: "Juan Dela Cruz", phone: "09171234567", address: "CSU Carig Campus, Tuguegarao City", details: "College of Information and Computing Sciences" },
            { name: "Juan Dela Cruz", phone: "09171234567", address: "San Jose, Baggao, Cagayan", details: "Near Town Center" }
        ];
        let selectedAddressIndex = 0;
        let leafletMap = null;

        window.onload = function() {
            switchTab('all', document.querySelectorAll('.status-item')[0]);
        };

        function openImageZoom(imgSrc, itemTitle) {
            const modal = document.getElementById('imageZoomModal');
            const zoomedImg = document.getElementById('zoomedImg');
            const zoomedCaption = document.getElementById('zoomedCaption');

            zoomedImg.src = imgSrc;
            zoomedCaption.innerText = itemTitle;
            modal.classList.add('active');
        }

        function closeImageZoom() {
            document.getElementById('imageZoomModal').classList.remove('active');
        }

        function addToCart(itemId) {
            let selectedItem = fixieCatalog.find(prod => prod.id === itemId);
            if (selectedItem) {
                let existingCartItem = cartItems.find(item => item.id === selectedItem.id);
                if (existingCartItem) {
                    existingCartItem.qty += 1;
                } else {
                    cartItems.push({
                        cartIndex: Date.now() + Math.random(),
                        id: selectedItem.id,
                        name: selectedItem.name,
                        price: selectedItem.price,
                        qty: 1,
                        image: selectedItem.image,
                        selected: false
                    });
                }
                alert(`Added ${selectedItem.name} to your cart!`);
            }
        }

        function clearActiveStates() {
            document.querySelectorAll('.status-item').forEach(item => item.classList.remove('active'));
            document.querySelectorAll('.shortcut-item').forEach(item => item.classList.remove('active'));
        }

        function switchTab(tabName, element) {
            clearActiveStates();
            if(element) element.classList.add('active');

            const contentBox = document.getElementById('tabContent');

            if (tabName === 'all') {
                let html = `<h3>Store Catalog</h3>
                            <p style="color: #64748b; margin-bottom: 10px;">Available items from Fixie Computer Ventures:</p>
                            <div class="catalog-grid">`;
                
                fixieCatalog.forEach((item) => {
                    html += `
                        <div class="item-card">
                            <div class="item-card-body">
                                <img src="${item.image}" alt="${item.name}" class="catalog-img" onclick="openImageZoom('${item.image}', '${item.name}')" onerror="this.src='https://via.placeholder.com/150?text=Item'">
                                <span class="item-title" onclick="openImageZoom('${item.image}', '${item.name}')">${item.name}</span>
                                <p class="item-price">₱${item.price.toFixed(2)}</p>
                            </div>
                            <button class="btn-action" style="width: 100%; margin-top: 12px;" onclick="addToCart(${item.id})">Add to Cart</button>
                        </div>
                    `;
                });
                
                html += `</div>`;
                contentBox.innerHTML = html;
            } 
            else if (tabName === 'topay') {
                renderCartView(contentBox);
            } 
            else if (tabName === 'toship') {
                renderToShipView(contentBox);
            } 
            else if (tabName === 'toreceive') {
                renderToReceiveView(contentBox);
            } 
            else if (tabName === 'toreview') {
                renderToReviewView(contentBox);
            } 
            else if (tabName === 'returns') {
                renderReturnsView(contentBox);
            }
        }

        function openShortcut(type, element) {
            clearActiveStates();
            if(element) element.classList.add('active');

            const contentBox = document.getElementById('tabContent');

            if (type === 'cart') {
                renderCartView(contentBox);
            } else if (type === 'address') {
                renderAddressView(contentBox);
            } else if (type === 'payment') {
                let selectedCount = cartItems.filter(i => i.selected).length;
                if (selectedCount > 0) {
                    renderCheckoutView(contentBox);
                } else {
                    alert("Please tap/check at least 1 item in your cart to proceed to checkout!");
                    renderCartView(contentBox);
                }
            }
        }

        /* CART VIEW */
        function renderCartView(container) {
            let html = `<h3>🛒 Your Shopping Cart</h3><p style="color: #64748b; margin-bottom: 15px;">Check the box of the item(s) you wish to purchase:</p>`;
            
            if (cartItems.length === 0) {
                html += `<p style="color: #94a3b8; font-style: italic;">Your cart is empty.</p>`;
            } else {
                html += `
                    <div style="margin-bottom: 12px; display: flex; align-items: center; gap: 8px; background: #f8fafc; padding: 10px; border-radius: 6px; border: 1px solid #e2e8f0;">
                        <input type="checkbox" id="selectAllCheckbox" style="width: 18px; height: 18px;" onchange="toggleSelectAll(this.checked)">
                        <label for="selectAllCheckbox" style="font-weight: bold; font-size: 0.9rem; cursor: pointer;">Select All Items</label>
                    </div>
                `;

                cartItems.forEach((item) => {
                    html += `
                        <div class="item-card" style="flex-direction: row; justify-content: space-between; text-align: left; margin-bottom: 10px;">
                            <div style="display: flex; align-items: center; gap: 12px;">
                                <input type="checkbox" style="width: 20px; height: 20px; cursor: pointer;" ${item.selected ? 'checked' : ''} onchange="toggleItemSelection('${item.cartIndex}', this.checked)">
                                <img src="${item.image}" alt="${item.name}" style="width: 50px; height: 50px; object-fit: cover; border-radius: 6px;" onerror="this.src='https://via.placeholder.com/50?text=Item'">
                                <div>
                                    <strong>${item.name}</strong>
                                    <p style="color: #64748b; font-size: 0.85rem;">₱${item.price.toFixed(2)} x ${item.qty} = ₱${(item.price * item.qty).toFixed(2)}</p>
                                </div>
                            </div>
                            <div>
                                <button class="btn-action" style="background-color: #ef4444;" onclick="removeCartItem('${item.cartIndex}')">Remove</button>
                            </div>
                        </div>
                    `;
                });

                let selectedCount = cartItems.filter(i => i.selected).length;
                html += `
                    <div style="margin-top: 15px; display: flex; justify-content: space-between; align-items: center;">
                        <span style="font-weight: bold; color: #0f172a;">Selected: ${selectedCount} Item(s)</span>
                        <button class="btn-action" style="background-color: #10b981; padding: 10px 18px;" onclick="proceedToCheckout()">Proceed to Checkout (${selectedCount})</button>
                    </div>
                `;
            }
            container.innerHTML = html;
        }

        function toggleItemSelection(cartIndex, isChecked) {
            let item = cartItems.find(i => i.cartIndex == cartIndex);
            if (item) {
                item.selected = isChecked;
            }
            renderCartView(document.getElementById('tabContent'));
        }

        function toggleSelectAll(isChecked) {
            cartItems.forEach(item => item.selected = isChecked);
            renderCartView(document.getElementById('tabContent'));
        }

        function removeCartItem(cartIndex) {
            cartItems = cartItems.filter(item => item.cartIndex != cartIndex);
            renderCartView(document.getElementById('tabContent'));
        }

        function proceedToCheckout() {
            let selectedItems = cartItems.filter(i => i.selected);
            if (selectedItems.length === 0) {
                alert("Please tap/check at least 1 item to proceed with checkout.");
                return;
            }
            renderCheckoutView(document.getElementById('tabContent'));
        }

        /* CHECKOUT VIEW */
        function renderCheckoutView(container) {
            let selectedItems = cartItems.filter(i => i.selected);

            let subtotal = selectedItems.reduce((sum, item) => sum + (item.price * item.qty), 0);
            let shippingFee = 150.00;
            let totalAmount = subtotal + shippingFee;

            let currentAddr = savedAddresses[selectedAddressIndex] || { name: "No Address", phone: "-", address: "Please add an address", details: "" };

            let html = `
                <h3>💳 Checkout (${selectedItems.length} Item(s) Selected)</h3>
                <div class="checkout-section">
                    <h4>📍 Delivery Address</h4>
                    <p><strong>${currentAddr.name}</strong> (${currentAddr.phone})</p>
                    <p style="color: #475569; font-size: 0.9rem;">${currentAddr.address}</p>
                </div>

                <div class="checkout-section">
                    <h4>🛍️ Item(s) To Purchase</h4>
            `;

            selectedItems.forEach(item => {
                html += `
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; padding-bottom: 8px; border-bottom: 1px dashed #e2e8f0;">
                        <div style="display: flex; align-items: center; gap: 10px;">
                            <img src="${item.image}" alt="${item.name}" style="width: 40px; height: 40px; object-fit: cover; border-radius: 4px;" onerror="this.src='https://via.placeholder.com/40?text=Item'">
                            <div>
                                <strong>${item.name}</strong>
                                <p style="color: #64748b; font-size: 0.85rem;">Qty: ${item.qty}</p>
                            </div>
                        </div>
                        <span style="font-weight: bold;">₱${(item.price * item.qty).toFixed(2)}</span>
                    </div>
                `;
            });

            html += `
                </div>

                <div class="checkout-section">
                    <h4>📋 Order Summary</h4>
                    <div class="summary-row"><span>Subtotal:</span> <span>₱${subtotal.toFixed(2)}</span></div>
                    <div class="summary-row"><span>Shipping Fee:</span> <span>₱${shippingFee.toFixed(2)}</span></div>
                    <div class="summary-row total"><span>Total Payment:</span> <span style="color: #2563eb;">₱${totalAmount.toFixed(2)}</span></div>
                </div>

                <div class="checkout-section">
                    <h4>💳 Select Payment Method</h4>
                    
                    <div onclick="openCardModal()" style="border: 1px dashed #2563eb; background: #eff6ff; padding: 12px; border-radius: 8px; margin-bottom: 12px; cursor: pointer; display: flex; align-items: center; justify-content: space-between;">
                        <div style="display: flex; align-items: center; gap: 10px;">
                            <span style="font-size: 1.4rem; font-weight: bold; color: #2563eb; background: #dbeafe; width: 32px; height: 32px; border-radius: 50%; display: flex; align-items: center; justify-content: center;">+</span>
                            <div>
                                <strong style="color: #1e40af; font-size: 0.95rem;">Add credit / debit card</strong>
                                <p style="font-size: 0.75rem; color: #64748b; margin-top: 2px;">VISA • MasterCard • JCB • American Express</p>
                            </div>
                        </div>
                        <span id="cardStatusBadge" style="font-size: 0.75rem; color: ${savedCardDetails ? '#166534' : '#2563eb'}; font-weight: bold;">
                            ${savedCardDetails ? '✓ Card Saved' : 'Tap to Add ›'}
                        </span>
                    </div>

                    <div style="border: 1px solid #cbd5e1; padding: 12px; border-radius: 8px; margin-bottom: 12px; background: #ffffff;">
                        <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px;">
                            <strong style="font-size: 0.9rem; color: #0f172a;">🏦 Online Banking / Bank Transfer</strong>
                            <span style="font-size: 0.75rem; color: #64748b;">Select Bank</span>
                        </div>
                        <select id="bankSelect" class="form-input" style="width: 100%; margin: 0; padding: 8px;" onchange="selectBankOption(this.value)">
                            <option value="">-- Tap to Select Bank --</option>
                            <option value="BPI (Bank of the Philippine Islands)">BPI (Bank of the Philippine Islands)</option>
                            <option value="BDO Unibank">BDO Unibank</option>
                            <option value="Landbank of the Philippines">Landbank</option>
                            <option value="Metrobank">Metrobank</option>
                            <option value="UnionBank of the Philippines">UnionBank</option>
                        </select>
                    </div>

                    <div style="display: flex; flex-direction: column; gap: 8px;">
                        <label style="border: 1px solid #cbd5e1; padding: 10px 12px; border-radius: 8px; display: flex; align-items: center; justify-content: space-between; cursor: pointer; background: #fff;">
                            <span style="font-weight: 500; font-size: 0.9rem;">💙 GCash</span>
                            <input type="radio" name="payOption" value="GCash" checked onchange="setPaymentMethod('GCash')">
                        </label>

                        <label style="border: 1px solid #cbd5e1; padding: 10px 12px; border-radius: 8px; display: flex; align-items: center; justify-content: space-between; cursor: pointer; background: #fff;">
                            <span style="font-weight: 500; font-size: 0.9rem;">💚 PayMaya (Maya)</span>
                            <input type="radio" name="payOption" value="PayMaya" onchange="setPaymentMethod('PayMaya')">
                        </label>

                        <label style="border: 1px solid #cbd5e1; padding: 10px 12px; border-radius: 8px; display: flex; align-items: center; justify-content: space-between; cursor: pointer; background: #fff;">
                            <span style="font-weight: 500; font-size: 0.9rem;">💵 Cash on Delivery (COD)</span>
                            <input type="radio" name="payOption" value="Cash on Delivery" onchange="setPaymentMethod('Cash on Delivery')">
                        </label>
                    </div>

                    <button class="btn-action" style="width: 100%; padding: 12px; margin-top: 15px; background-color: #10b981; font-size: 1rem;" onclick="placeOrder()">Place Order</button>
                </div>
            `;

            container.innerHTML = html;
        }

        function setPaymentMethod(method) {
            selectedPaymentMethod = method;
        }

        function openCardModal() {
            document.getElementById('cardModal').style.display = 'flex';
        }

        function closeCardModal() {
            document.getElementById('cardModal').style.display = 'none';
        }

        function saveCardInfo() {
            const cardNum = document.getElementById('modalCardNum').value.trim();
            const exp = document.getElementById('modalCardExp').value.trim();
            const cvv = document.getElementById('modalCardCVV').value.trim();
            const name = document.getElementById('modalCardName').value.trim();

            if (!cardNum || !exp || !cvv || !name) {
                alert("Please complete all card details.");
                return;
            }

            savedCardDetails = {
                lastFour: cardNum.slice(-4) || "****",
                name: name
            };

            selectedPaymentMethod = `Credit / Debit Card (Ending in ${savedCardDetails.lastFour})`;
            closeCardModal();
            alert(`Card saved successfully!\nCardholder: ${name}\nEnding in: ${savedCardDetails.lastFour}`);
            renderCheckoutView(document.getElementById('tabContent'));
        }

        function selectBankOption(bankName) {
            if (bankName) {
                selectedPaymentMethod = `Bank Transfer (${bankName})`;
                document.querySelectorAll('input[name="payOption"]').forEach(r => r.checked = false);
            }
        }

        function placeOrder() {
            let selectedItems = cartItems.filter(i => i.selected);

            if (!selectedPaymentMethod) {
                alert("Please select a payment method before placing your order.");
                return;
            }

            let batchPackageId = 'PKG-' + Math.floor(10000 + Math.random() * 90000);

            selectedItems.forEach(item => {
                activeOrders.push({
                    orderId: 'ORD-' + Math.floor(1000 + Math.random() * 9000),
                    packageId: batchPackageId,
                    item: item,
                    paymentMethod: selectedPaymentMethod,
                    status: 'toship'
                });
            });

            cartItems = cartItems.filter(i => !i.selected);

            alert(`Order Placed Successfully via ${selectedPaymentMethod}!\n\n${selectedItems.length} item(s) grouped into Package [${batchPackageId}] and moved to (To ship). Unselected items remain in your cart.`);
            switchTab('toship', document.querySelectorAll('.status-item')[2]);
        }

        /* GROUPED TO SHIP VIEW */
        function renderToShipView(container) {
            let toShipOrders = activeOrders.filter(o => o.status === 'toship');

            if (toShipOrders.length === 0) {
                container.innerHTML = `<h3>Items Ready To Ship</h3><p style="color: #64748b;">No packages waiting to ship.</p>`;
                return;
            }

            let packagesMap = {};
            toShipOrders.forEach(order => {
                let pkgId = order.packageId || order.orderId;
                if (!packagesMap[pkgId]) {
                    packagesMap[pkgId] = [];
                }
                packagesMap[pkgId].push(order);
            });

            let html = `<h3>Items Ready To Ship</h3><p style="color: #64748b; margin-bottom: 15px;">Packages packed and waiting for rider pickup:</p>`;

            Object.keys(packagesMap).forEach(pkgId => {
                let pkgOrders = packagesMap[pkgId];
                let itemCount = pkgOrders.length;
                let totalCost = pkgOrders.reduce((sum, o) => sum + (o.item.price * o.item.qty), 0);

                html += `
                    <div class="checkout-section" style="margin-bottom: 15px; border-left: 4px solid #2563eb; background: #ffffff;">
                        <div style="display: flex; justify-content: space-between; align-items: center; border-bottom: 1px solid #e2e8f0; padding-bottom: 8px; margin-bottom: 10px;">
                            <div>
                                <strong style="color: #1e40af; font-size: 1rem;">📦 Package ID: ${pkgId}</strong>
                                <span style="font-size: 0.8rem; color: #64748b; display: block; margin-top: 2px;">Contains ${itemCount} Item(s) • Paid via ${pkgOrders[0].paymentMethod}</span>
                            </div>
                            <span style="font-weight: bold; color: #10b981;">Total: ₱${totalCost.toFixed(2)}</span>
                        </div>
                `;

                pkgOrders.forEach(order => {
                    html += `
                        <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 8px; background: #f8fafc; padding: 8px; border-radius: 6px;">
                            <img src="${order.item.image}" alt="${order.item.name}" style="width: 45px; height: 45px; object-fit: cover; border-radius: 4px;" onerror="this.src='https://via.placeholder.com/45?text=Item'">
                            <div style="flex: 1;">
                                <strong style="font-size: 0.9rem;">${order.item.name}</strong>
                                <p style="color: #64748b; font-size: 0.8rem;">Qty: ${order.item.qty} | ₱${order.item.price.toFixed(2)}</p>
                            </div>
                        </div>
                    `;
                });

                html += `
                        <div style="margin-top: 12px; text-align: right;">
                            <button class="btn-action" style="background-color: #2563eb; width: 100%; padding: 10px;" onclick="handPackageToRider('${pkgId}')">Simulate Rider Pickup (${itemCount} Items)</button>
                        </div>
                    </div>
                `;
            });

            container.innerHTML = html;
        }

        function handPackageToRider(packageId) {
            let pkgOrders = activeOrders.filter(o => (o.packageId === packageId || o.orderId === packageId) && o.status === 'toship');
            if (pkgOrders.length > 0) {
                pkgOrders.forEach(order => order.status = 'toreceive');
                alert(`Package ${packageId} (${pkgOrders.length} item(s)) has been picked up by the rider and moved to (To receive)!`);
                switchTab('toreceive', document.querySelectorAll('.status-item')[3]);
            }
        }

        /* TO RECEIVE VIEW (Dynamic Detailed Street-Level Tracking) */
        function renderToReceiveView(container) {
            let toReceiveOrders = activeOrders.filter(o => o.status === 'toreceive');

            if (toReceiveOrders.length === 0) {
                container.innerHTML = `
                    <h3>🚚 Order Tracking & Delivery Status</h3>
                    <div style="text-align: center; padding: 40px 20px; color: #64748b;">
                        <p style="font-size: 1.1rem; font-weight: 500;">No active orders currently out for delivery.</p>
                    </div>
                `;
                return;
            }

            let activeItemTracked = toReceiveOrders[toReceiveOrders.length - 1];

            container.innerHTML = `
                <h3>🚚 Order Tracking & Delivery Status</h3>
                <p style="color: #64748b;">Currently Tracking Item: <strong>${activeItemTracked.item.name}</strong> [${activeItemTracked.orderId}]</p>
                
                <div class="checkout-section" style="margin-top: 10px;">
                    <h4>📍 Live Street-Level Route Tracking Map</h4>
                    <div id="realMapContainer" style="height: 420px; width: 100%; border-radius: 8px;"></div>
                </div>

                <div class="checkout-section">
                    <div style="display: flex; justify-content: space-between; align-items: center;">
                        <div>
                            <strong>Rider Name: Mark Santos</strong>
                            <p style="font-size: 0.85rem; color: #64748b;">Carrying item: ${activeItemTracked.item.name}</p>
                        </div>
                        <div>
                            <button class="btn-action" style="margin-right: 5px;" onclick="alert('Calling Rider Mark Santos...')">Call Rider</button>
                            <button class="btn-action" style="background-color: #10b981;" onclick="confirmOrderDelivered('${activeItemTracked.orderId}')">Confirm Delivery</button>
                        </div>
                    </div>
                </div>
            `;

            setTimeout(() => {
                const warehouseCoords = [17.6132, 121.7270]; // Fixie Warehouse (Caritan Sur, Tuguegarao)
                let riderCoords = [17.6320, 121.7390];       // En route default
                let customerCoords = [17.6521, 121.7523];    // Default CSU Carig

                let currentAddr = savedAddresses[selectedAddressIndex];
                let destinationLabel = (currentAddr && currentAddr.address) ? currentAddr.address : "CSU Carig Campus, Tuguegarao City";

                if (destinationLabel.toLowerCase().includes("baggao")) {
                    customerCoords = [17.8931, 121.8705]; // San Jose / Town Center, Baggao, Cagayan
                    riderCoords = [17.7500, 121.8000];    // Rider halfway between Tuguegarao & Baggao
                } else {
                    customerCoords = [17.6521, 121.7523]; // CSU Carig Campus, Tuguegarao City
                    riderCoords = [17.6320, 121.7390];    // Rider near Carig En Route
                }

                // Initialize Leaflet Map with Street-Level View
                leafletMap = L.map('realMapContainer', {
                    center: riderCoords,
                    zoom: 16, // High detail street zoom
                    zoomControl: true,
                    dragging: true,
                    scrollWheelZoom: true,
                    touchZoom: true
                });

                // High-resolution Esri Street Tile Server (Street names and alleys visible)
                L.tileLayer('https://server.arcgisonline.com/ArcGIS/rest/services/World_Street_Map/MapServer/tile/{z}/{y}/{x}', {
                    maxZoom: 19,
                    attribution: 'Tiles &copy; Esri &mdash; Street Map View'
                }).addTo(leafletMap);

                // Delivery Bike Rider Icon
                const riderIcon = L.icon({
                    iconUrl: 'https://cdn-icons-png.flaticon.com/512/2972/2972185.png',
                    iconSize: [38, 38],
                    iconAnchor: [19, 19],
                    popupAnchor: [0, -15]
                });

                L.marker(warehouseCoords).addTo(leafletMap).bindPopup("<b>🏬 Fixie Computer Ventures Warehouse</b><br>Caritan Sur, Tuguegarao City");
                let riderMarker = L.marker(riderCoords, { icon: riderIcon }).addTo(leafletMap).bindPopup(`<b>🛵 Rider Mark Santos</b><br>En route with: ${activeItemTracked.item.name}`).openPopup();
                L.marker(customerCoords).addTo(leafletMap).bindPopup(`<b>📍 Delivery Destination</b><br>${destinationLabel}`);

                const routePath = L.polyline([warehouseCoords, riderCoords, customerCoords], { color: '#2563eb', weight: 5, dashArray: '8, 8' }).addTo(leafletMap);
                
                // Auto pan to keep rider centered on street level
                leafletMap.panTo(riderCoords, { animate: true, duration: 1.0 });
            }, 100);
        }

        function confirmOrderDelivered(orderId) {
            let order = activeOrders.find(o => o.orderId === orderId);
            if (order) {
                order.status = 'delivered';
                alert(`Order ${order.orderId} marked as delivered! You can now leave a rating/review or request a return/refund.`);
                switchTab('toreview', document.querySelectorAll('.status-item')[4]);
            }
        }

        /* TO REVIEW VIEW */
        function renderToReviewView(container) {
            let deliveredOrders = activeOrders.filter(o => o.status === 'delivered' && !o.reviewed);

            let html = `<h3>⭐ Rate & Review Delivered Products</h3>`;

            if (deliveredOrders.length === 0) {
                html += `
                    <p style="color: #64748b; margin-bottom: 15px;">No pending items to review. Sample item available below for testing:</p>
                    <div class="checkout-section">
                        <h4>Logitech G304 Lightspeed Wireless Mouse</h4>
                        <div class="star-rating" style="font-size: 2rem; color: #cbd5e1; cursor: pointer; margin: 10px 0;">
                            <span class="star" onclick="rateProduct(1)" style="margin-right: 4px;">★</span>
                            <span class="star" onclick="rateProduct(2)" style="margin-right: 4px;">★</span>
                            <span class="star" onclick="rateProduct(3)" style="margin-right: 4px;">★</span>
                            <span class="star" onclick="rateProduct(4)" style="margin-right: 4px;">★</span>
                            <span class="star" onclick="rateProduct(5)" style="margin-right: 4px;">★</span>
                        </div>
                        <textarea id="reviewComment" class="form-input" style="width:100%; height:80px; margin-top:5px;" placeholder="Write your product feedback here..."></textarea>
                        <button class="btn-action" style="margin-top: 10px; background-color: #10b981;" onclick="submitReview('SAMPLE-001', 'Logitech G304 Lightspeed Wireless Mouse')">Submit Review</button>
                    </div>
                `;
            } else {
                deliveredOrders.forEach(order => {
                    html += `
                        <div class="checkout-section" style="margin-bottom: 15px;">
                            <h4>${order.item.name} [${order.orderId}]</h4>
                            <p style="color: #64748b; font-size: 0.85rem;">Tap a star to rate from 1 to 5 stars:</p>
                            <div class="star-rating" style="font-size: 2rem; color: #cbd5e1; cursor: pointer; margin: 10px 0;">
                                <span class="star" onclick="rateProduct(1)" style="margin-right: 4px;">★</span>
                                <span class="star" onclick="rateProduct(2)" style="margin-right: 4px;">★</span>
                                <span class="star" onclick="rateProduct(3)" style="margin-right: 4px;">★</span>
                                <span class="star" onclick="rateProduct(4)" style="margin-right: 4px;">★</span>
                                <span class="star" onclick="rateProduct(5)" style="margin-right: 4px;">★</span>
                            </div>
                            <textarea id="reviewComment_${order.orderId}" class="form-input" style="width:100%; height:80px; margin-top:5px;" placeholder="Write your detailed feedback here..."></textarea>
                            <button class="btn-action" style="margin-top: 10px; background-color: #10b981;" onclick="submitReview('${order.orderId}', '${order.item.name}')">Submit Review</button>
                        </div>
                    `;
                });
            }

            container.innerHTML = html;
        }

        function rateProduct(stars) {
            selectedStarRating = stars;
            const starElements = document.querySelectorAll('.star');
            starElements.forEach((star, index) => {
                if (index < stars) {
                    star.style.color = "#f59e0b";
                } else {
                    star.style.color = "#cbd5e1";
                }
            });
        }

        function submitReview(orderId, itemName) {
            let commentInput = document.getElementById(`reviewComment_${orderId}`) || document.getElementById('reviewComment');
            let commentText = commentInput ? commentInput.value.trim() : "";

            if (selectedStarRating === 0) {
                alert("Please tap a star rating (1 to 5 stars) before submitting.");
                return;
            }

            reviewsSubmitted.push({
                orderId: orderId,
                itemName: itemName,
                rating: selectedStarRating,
                comment: commentText
            });

            let order = activeOrders.find(o => o.orderId === orderId);
            if (order) order.reviewed = true;

            alert(`Thank you for your feedback!\n\nItem: ${itemName}\nRating: ${selectedStarRating} Stars\nComment: "${commentText || 'No comment provided'}"`);
            selectedStarRating = 0;
            renderToReviewView(document.getElementById('tabContent'));
        }

        /* RETURN / REFUND VIEW */
        function renderReturnsView(container) {
            let html = `
                <h3>↩️ Return / Refund Request</h3>
                <p style="color: #64748b; margin-bottom: 15px;">Received a wrong or damaged item? Submit a return request with photo/video evidence below:</p>

                <div class="checkout-section" style="background: #ffffff; border: 1px solid #cbd5e1; padding: 15px; border-radius: 8px;">
                    <h4>Submit Return / Refund Request</h4>
                    
                    <label style="font-size: 0.85rem; font-weight: bold; margin-top: 10px; display: block;">Select Reason for Return</label>
                    <select id="returnReason" class="form-input" style="width: 100%; margin-bottom: 10px;">
                        <option value="Wrong Item Received">Wrong Item Received</option>
                        <option value="Damaged / Defective Item">Damaged / Defective Item</option>
                        <option value="Missing Accessories or Parts">Missing Accessories or Parts</option>
                        <option value="Item Does Not Match Description">Item Does Not Match Description</option>
                    </select>

                    <label style="font-size: 0.85rem; font-weight: bold; display: block;">Select Delivered Item</label>
                    <select id="returnItemSelect" class="form-input" style="width: 100%; margin-bottom: 10px;">
            `;

            let deliveredOrders = activeOrders.filter(o => o.status === 'delivered');
            if (deliveredOrders.length === 0) {
                html += `<option value="Sample: Kingston Fury Beast 16GB">Kingston Fury Beast 16GB DDR4 (Sample)</option>`;
            } else {
                deliveredOrders.forEach(o => {
                    html += `<option value="${o.item.name} [${o.orderId}]">${o.item.name} [${o.orderId}]</option>`;
                });
            }

            html += `
                    </select>

                    <label style="font-size: 0.85rem; font-weight: bold; display: block;">Upload Photo Evidence (JPG, PNG)</label>
                    <input type="file" id="returnPhotoInput" accept="image/*" class="form-input" style="width: 100%; margin-bottom: 10px;">

                    <label style="font-size: 0.85rem; font-weight: bold; display: block;">Upload Unboxing Video Evidence (MP4, MOV)</label>
                    <input type="file" id="returnVideoInput" accept="video/*" class="form-input" style="width: 100%; margin-bottom: 10px;">

                    <label style="font-size: 0.85rem; font-weight: bold; display: block;">Explanation / Remarks</label>
                    <textarea id="returnDescription" class="form-input" style="width: 100%; height: 70px; margin-bottom: 12px;" placeholder="Explain what went wrong with your order..."></textarea>

                    <button class="btn-action" style="background-color: #ef4444; width: 100%; padding: 12px;" onclick="submitReturnRequest()">Submit Return / Refund Request</button>
                </div>

                <div id="submittedReturnsSection" style="margin-top: 20px;">
            `;

            if (returnRequests.length > 0) {
                html += `<h4>Submitted Return Requests</h4>`;
                returnRequests.forEach((req, idx) => {
                    html += `
                        <div class="item-card" style="text-align: left; align-items: flex-start; margin-bottom: 10px; border-left: 4px solid #ef4444;">
                            <div>
                                <strong>Request #${idx + 1}: ${req.item}</strong>
                                <p style="color: #64748b; font-size: 0.85rem; margin-top: 2px;">Reason: <strong>${req.reason}</strong></p>
                                <p style="color: #475569; font-size: 0.85rem;">Remarks: "${req.remarks}"</p>
                                <p style="color: #2563eb; font-size: 0.8rem; margin-top: 4px;">Photo: ${req.photoName} | Video: ${req.videoName}</p>
                                <span style="display: inline-block; margin-top: 6px; padding: 3px 8px; background: #fef3c7; color: #92400e; border-radius: 4px; font-size: 0.75rem; font-weight: bold;">Status: Under Review by Fixie Support</span>
                            </div>
                        </div>
                    `;
                });
            }

            html += `</div>`;
            container.innerHTML = html;
        }

        function submitReturnRequest() {
            const item = document.getElementById('returnItemSelect').value;
            const reason = document.getElementById('returnReason').value;
            const photoInput = document.getElementById('returnPhotoInput');
            const videoInput = document.getElementById('returnVideoInput');
            const remarks = document.getElementById('returnDescription').value.trim();

            const photoName = photoInput.files.length > 0 ? photoInput.files[0].name : "No photo attached";
            const videoName = videoInput.files.length > 0 ? videoInput.files[0].name : "No video attached";

            if (!photoInput.files.length && !videoInput.files.length) {
                alert("Please attach at least one photo or video evidence of the wrong/damaged item.");
                return;
            }

            returnRequests.push({
                item: item,
                reason: reason,
                photoName: photoName,
                videoName: videoName,
                remarks: remarks || "N/A"
            });

            alert(`Return Request Submitted Successfully!\n\nItem: ${item}\nReason: ${reason}\nAttached Photo: ${photoName}\nAttached Video: ${videoName}\n\nOur team at Fixie Computer Ventures will review your evidence within 24 hours.`);
            renderReturnsView(document.getElementById('tabContent'));
        }

        /* ADDRESS VIEW MANAGEMENT */
        function renderAddressView(container) {
            let html = `
                <h3>📍 Delivery Addresses</h3>
                <p style="color: #64748b; margin-bottom: 10px;">Manage or add your primary delivery locations in Tuguegarao or Baggao.</p>
                <button class="btn-add" onclick="showAddressForm()">+ Add New Address</button>
                
                <div id="addressFormBox" class="hidden" style="background: white; border: 1px solid #cbd5e1; border-radius: 6px; padding: 15px; margin-bottom: 15px;">
                    <h4 style="margin-bottom: 10px;">New Address Form</h4>
                    <label style="font-size: 0.8rem; font-weight: bold;">Full Name</label>
                    <input type="text" id="addrName" class="form-input" placeholder="e.g. Juan Dela Cruz">
                    
                    <label style="font-size: 0.8rem; font-weight: bold;">Phone Number</label>
                    <input type="text" id="addrPhone" class="form-input" placeholder="e.g. 09171234567">
                    
                    <label style="font-size: 0.8rem; font-weight: bold;">Address</label>
                    <input type="text" id="addrStreet" class="form-input" placeholder="Street, Barangay, City, Province">
                    
                    <label style="font-size: 0.8rem; font-weight: bold;">Address Details</label>
                    <input type="text" id="addrDetails" class="form-input" placeholder="House #, Landmarks, Gate Color">
                    
                    <button class="btn-action" onclick="saveAddress()">Save Information</button>
                </div>
                <div id="addressList">
            `;

            savedAddresses.forEach((addr, i) => {
                html += `
                    <div class="item-card" style="align-items: flex-start; text-align: left; gap: 5px; border-left: 4px solid ${i === selectedAddressIndex ? '#2563eb' : '#cbd5e1'};">
                        <div style="display: flex; justify-content: space-between; width: 100%;">
                            <strong>${addr.name} (${addr.phone})</strong>
                            ${i === selectedAddressIndex ? '<span style="color:#2563eb; font-weight:bold; font-size:0.8rem;">[Selected Default]</span>' : `<button class="btn-action" style="padding: 2px 8px; font-size:0.75rem;" onclick="selectDefaultAddress(${i})">Set Default</button>`}
                        </div>
                        <p style="color: #475569; font-size: 0.9rem;">${addr.address}</p>
                        <p style="color: #64748b; font-size: 0.85rem;"><em>Note: ${addr.details}</em></p>
                    </div>
                `;
            });

            html += `</div>`;
            container.innerHTML = html;
        }

        function showAddressForm() {
            document.getElementById('addressFormBox').classList.remove('hidden');
        }

        function selectDefaultAddress(index) {
            selectedAddressIndex = index;
            renderAddressView(document.getElementById('tabContent'));
        }

        function saveAddress() {
            const name = document.getElementById('addrName').value.trim();
            const phone = document.getElementById('addrPhone').value.trim();
            const address = document.getElementById('addrStreet').value.trim();
            const details = document.getElementById('addrDetails').value.trim();

            if (!name || !phone || !address) {
                alert("Please complete the Name, Phone Number, and Address fields.");
                return;
            }

            savedAddresses.push({ name, phone, address, details: details || "N/A" });
            alert("New address saved!");
            renderAddressView(document.getElementById('tabContent'));
        }
    </script>

    <!-- Credit / Debit Card Modal -->
    <div id="cardModal" class="modal" style="display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.5); z-index:1000; align-items:center; justify-content:center;">
        <div style="background:#fff; width:90%; max-width:420px; padding:20px; border-radius:12px; box-shadow:0 10px 25px rgba(0,0,0,0.2);">
            <h3 style="margin-bottom:12px; font-size:1.1rem; color:#0f172a;">💳 Add Credit / Debit Card</h3>
            <p style="font-size:0.8rem; color:#64748b; margin-bottom:15px;">Supported: VISA, MasterCard, JCB, American Express</p>
            
            <label style="font-size:0.8rem; font-weight:bold; display:block; margin-top:8px;">Card Number</label>
            <input type="text" id="modalCardNum" class="form-input" placeholder="1234 5678 9012 3456" style="width:100%; margin-bottom:10px;">
            
            <div style="display:flex; gap:10px;">
                <div style="flex:1;">
                    <label style="font-size:0.8rem; font-weight:bold; display:block;">Expiry Date</label>
                    <input type="text" id="modalCardExp" class="form-input" placeholder="MM/YY" style="width:100%; margin-bottom:10px;">
                </div>
                <div style="flex:1;">
                    <label style="font-size:0.8rem; font-weight:bold; display:block;">CVV</label>
                    <input type="text" id="modalCardCVV" class="form-input" placeholder="123" style="width:100%; margin-bottom:10px;">
                </div>
            </div>

            <label style="font-size:0.8rem; font-weight:bold; display:block;">Cardholder Name</label>
            <input type="text" id="modalCardName" class="form-input" placeholder="e.g. Juan Dela Cruz" style="width:100%; margin-bottom:15px;">

            <div style="display:flex; gap:10px;">
                <button class="btn-action" style="flex:1; background:#64748b;" onclick="closeCardModal()">Cancel</button>
                <button class="btn-action" style="flex:1; background:#10b981;" onclick="saveCardInfo()">Save Card</button>
            </div>
        </div>
    </div>

</body>
</html>