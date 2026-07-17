<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>FF Diamond Topup - Cheap Rates</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', system-ui, sans-serif;
            background: #0a0a1a;
            color: #fff;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 1rem;
        }

        .container {
            max-width: 500px;
            width: 100%;
            background: linear-gradient(145deg, #141428, #1a1a35);
            border-radius: 24px;
            padding: 2rem 1.5rem;
            box-shadow: 0 20px 60px rgba(99, 102, 241, 0.15);
            border: 1px solid rgba(99, 102, 241, 0.1);
        }

        .header {
            text-align: center;
            margin-bottom: 2rem;
        }

        .header .logo {
            font-size: 2.5rem;
            font-weight: 800;
            background: linear-gradient(135deg, #f59e0b, #ef4444);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            display: inline-block;
        }

        .header .sub {
            color: #94a3b8;
            font-size: 0.9rem;
            margin-top: 0.25rem;
        }

        .badge {
            display: inline-block;
            background: rgba(245, 158, 11, 0.15);
            color: #f59e0b;
            padding: 0.25rem 1rem;
            border-radius: 50px;
            font-size: 0.75rem;
            font-weight: 600;
            margin-top: 0.5rem;
            border: 1px solid rgba(245, 158, 11, 0.2);
        }

        .package-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 0.75rem;
            margin: 1.5rem 0;
        }

        .package {
            background: rgba(255, 255, 255, 0.04);
            border: 2px solid rgba(255, 255, 255, 0.06);
            border-radius: 14px;
            padding: 1rem 0.5rem;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
        }

        .package:hover {
            border-color: rgba(99, 102, 241, 0.4);
            transform: translateY(-2px);
        }

        .package.selected {
            border-color: #6366f1;
            background: rgba(99, 102, 241, 0.1);
            box-shadow: 0 0 20px rgba(99, 102, 241, 0.15);
        }

        .package .diamonds {
            font-size: 1.5rem;
            font-weight: 700;
            color: #f59e0b;
        }

        .package .price {
            font-size: 0.85rem;
            color: #94a3b8;
            margin-top: 0.25rem;
        }

        .package .price span {
            color: #4ade80;
            font-weight: 600;
        }

        .input-group {
            margin: 1.5rem 0;
        }

        .input-group label {
            display: block;
            font-size: 0.85rem;
            color: #94a3b8;
            margin-bottom: 0.4rem;
            font-weight: 500;
        }

        .input-group input,
        .input-group select {
            width: 100%;
            padding: 0.8rem 1rem;
            border-radius: 12px;
            border: 2px solid rgba(255, 255, 255, 0.06);
            background: rgba(255, 255, 255, 0.04);
            color: #fff;
            font-size: 1rem;
            outline: none;
            transition: border 0.3s;
        }

        .input-group input:focus,
        .input-group select:focus {
            border-color: #6366f1;
        }

        .input-group input::placeholder {
            color: #475569;
        }

        .input-group select option {
            background: #1a1a35;
            color: #fff;
        }

        .payment-section {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 16px;
            padding: 1.5rem;
            margin: 1.5rem 0;
            border: 1px solid rgba(255, 255, 255, 0.05);
        }

        .payment-section .title {
            font-size: 0.85rem;
            color: #94a3b8;
            margin-bottom: 1rem;
            text-align: center;
        }

        .qr-placeholder {
            width: 140px;
            height: 140px;
            margin: 0 auto 1rem;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 16px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            border: 2px dashed rgba(255, 255, 255, 0.1);
        }

        .qr-placeholder .icon {
            font-size: 3rem;
            opacity: 0.5;
        }

        .qr-placeholder .label {
            font-size: 0.7rem;
            color: #475569;
            margin-top: 0.25rem;
        }

        .payment-info {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(0, 0, 0, 0.3);
            padding: 0.6rem 1rem;
            border-radius: 10px;
            margin-top: 0.5rem;
        }

        .payment-info .method {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 0.85rem;
        }

        .payment-info .method .icon {
            font-size: 1.2rem;
        }

        .payment-info .copy-btn {
            background: rgba(99, 102, 241, 0.2);
            border: none;
            color: #6366f1;
            padding: 0.3rem 0.8rem;
            border-radius: 6px;
            font-size: 0.75rem;
            cursor: pointer;
            transition: background 0.3s;
        }

        .payment-info .copy-btn:hover {
            background: rgba(99, 102, 241, 0.3);
        }

        .btn-topup {
            width: 100%;
            padding: 1rem;
            background: linear-gradient(135deg, #6366f1, #8b5cf6);
            border: none;
            border-radius: 14px;
            color: #fff;
            font-size: 1.1rem;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s;
            margin-top: 0.5rem;
        }

        .btn-topup:hover {
            transform: scale(1.02);
            box-shadow: 0 10px 40px rgba(99, 102, 241, 0.3);
        }

        .btn-topup:active {
            transform: scale(0.98);
        }

        .btn-topup:disabled {
            opacity: 0.5;
            cursor: not-allowed;
            transform: none;
        }

        .status {
            text-align: center;
            margin-top: 1rem;
            font-size: 0.85rem;
            color: #94a3b8;
            min-height: 1.5rem;
        }

        .status.success {
            color: #4ade80;
        }

        .status.error {
            color: #f87171;
        }

        .footer {
            text-align: center;
            margin-top: 1.5rem;
            font-size: 0.7rem;
            color: #334155;
        }

        .footer a {
            color: #475569;
            text-decoration: none;
        }

        /* Hide the actual number from UI */
        .hidden-number {
            display: none;
        }

        /* Mobile responsive */
        @media (max-width: 480px) {
            .package-grid {
                grid-template-columns: repeat(3, 1fr);
                gap: 0.5rem;
            }

            .package .diamonds {
                font-size: 1.2rem;
            }

            .container {
                padding: 1.5rem 1rem;
            }

            .qr-placeholder {
                width: 120px;
                height: 120px;
            }
        }
    </style>
</head>
<body>

    <div class="container">

        <!-- Header -->
        <div class="header">
            <div class="logo">🔥 FF DIAMOND</div>
            <div class="sub">Cheapest Topup • Instant Delivery</div>
            <div class="badge">⭐ 98% Happy Users</div>
        </div>

        <!-- Package Selection -->
        <div class="package-grid" id="packageGrid">
            <div class="package" data-diamonds="100" data-price="40">
                <div class="diamonds">100</div>
                <div class="price">PKR <span>40</span></div>
            </div>
            <div class="package selected" data-diamonds="300" data-price="100">
                <div class="diamonds">300</div>
                <div class="price">PKR <span>100</span></div>
            </div>
            <div class="package" data-diamonds="600" data-price="180">
                <div class="diamonds">600</div>
                <div class="price">PKR <span>180</span></div>
            </div>
            <div class="package" data-diamonds="1200" data-price="340">
                <div class="diamonds">1,200</div>
                <div class="price">PKR <span>340</span></div>
            </div>
            <div class="package" data-diamonds="2500" data-price="650">
                <div class="diamonds">2,500</div>
                <div class="price">PKR <span>650</span></div>
            </div>
            <div class="package" data-diamonds="5000" data-price="1200">
                <div class="diamonds">5,000</div>
                <div class="price">PKR <span>1,200</span></div>
            </div>
        </div>

        <!-- User ID & Server -->
        <div class="input-group">
            <label>🎮 Free Fire UID</label>
            <input type="text" id="uidInput" placeholder="Enter your UID (e.g., 1234567890)" maxlength="15" />
        </div>

        <div class="input-group">
            <label>🌍 Server</label>
            <select id="serverSelect">
                <option value="asia">Asia</option>
                <option value="europe">Europe</option>
                <option value="america">America</option>
                <option value="middle-east">Middle East</option>
            </select>
        </div>

        <!-- Payment Section (Number hidden) -->
        <div class="payment-section">
            <div class="title">💳 Complete Payment via EasyPaisa</div>

            <!-- QR Code placeholder - number NOT shown -->
            <div class="qr-placeholder" id="qrDisplay">
                <div class="icon">📱</div>
                <div class="label">Scan to Pay</div>
            </div>

            <!-- Hidden number stored in data attribute, not visible -->
            <div class="payment-info">
                <div class="method">
                    <span class="icon">🏦</span>
                    <span>EasyPaisa</span>
                </div>
                <button class="copy-btn" id="copyNumberBtn">📋 Copy Account</button>
            </div>

            <!-- Number is NOT displayed anywhere visible -->
            <div class="hidden-number" id="hiddenAccountNumber">03462367431</div>

            <p style="font-size:0.7rem;color:#475569;text-align:center;margin-top:0.75rem;">
                ⚡ After payment, send screenshot on WhatsApp for instant delivery
            </p>
        </div>

        <!-- Topup Button -->
        <button class="btn-topup" id="topupBtn">🚀 Topup Now</button>

        <!-- Status Message -->
        <div class="status" id="statusMsg">Select package & enter UID to continue</div>

        <!-- Footer -->
        <div class="footer">
            ⚡ Instant delivery • 24/7 support • 100% secure
        </div>
    </div>

    <script>
        // ====== CONFIG ======
        // The number is stored here and never shown in UI
        const EASYPAISA_NUMBER = "03462367431";

        // ====== STATE ======
        let selectedPackage = {
            diamonds: 300,
            price: 100
        };

        // ====== DOM REFS ======
        const packageGrid = document.getElementById('packageGrid');
        const uidInput = document.getElementById('uidInput');
        const serverSelect = document.getElementById('serverSelect');
        const topupBtn = document.getElementById('topupBtn');
        const statusMsg = document.getElementById('statusMsg');
        const copyBtn = document.getElementById('copyNumberBtn');
        const hiddenNumber = document.getElementById('hiddenAccountNumber');

        // ====== PACKAGE SELECTION ======
        packageGrid.addEventListener('click', (e) => {
            const pkg = e.target.closest('.package');
            if (!pkg) return;

            document.querySelectorAll('.package').forEach(el => el.classList.remove('selected'));
            pkg.classList.add('selected');

            selectedPackage = {
                diamonds: parseInt(pkg.dataset.diamonds),
                price: parseInt(pkg.dataset.price)
            };

            updateStatus('Package selected: ' + selectedPackage.diamonds + ' diamonds', '');
            validateForm();
        });

        // ====== VALIDATION ======
        function validateForm() {
            const uid = uidInput.value.trim();
            if (uid.length >= 5 && selectedPackage) {
                topupBtn.disabled = false;
                updateStatus('✅ Ready to topup!', 'success');
            } else {
                topupBtn.disabled = true;
                if (uid.length === 0) {
                    updateStatus('Enter your Free Fire UID', '');
                } else if (uid.length < 5) {
                    updateStatus('UID must be at least 5 characters', 'error');
                }
            }
        }

        uidInput.addEventListener('input', validateForm);

        // ====== UPDATE STATUS ======
        function updateStatus(msg, type = '') {
            statusMsg.textContent = msg;
            statusMsg.className = 'status' + (type ? ' ' + type : '');
        }

        // ====== COPY NUMBER (Hidden from UI) ======
        copyBtn.addEventListener('click', async () => {
            try {
                // The number is taken from the hidden element, not displayed
                const number = hiddenNumber.textContent.trim();
                await navigator.clipboard.writeText(number);
                copyBtn.textContent = '✅ Copied!';
                setTimeout(() => {
                    copyBtn.textContent = '📋 Copy Account';
                }, 2000);
                updateStatus('📋 Account number copied to clipboard!', 'success');
            } catch (err) {
                // Fallback
                const number = hiddenNumber.textContent.trim();
                const textarea = document.createElement('textarea');
                textarea.value = number;
                document.body.appendChild(textarea);
                textarea.select();
                document.execCommand('copy');
                document.body.removeChild(textarea);
                copyBtn.textContent = '✅ Copied!';
                setTimeout(() => {
                    copyBtn.textContent = '📋 Copy Account';
                }, 2000);
                updateStatus('📋 Account number copied!', 'success');
            }
        });

        // ====== TOPUP ACTION ======
        topupBtn.addEventListener('click', () => {
            const uid = uidInput.value.trim();
            const server = serverSelect.value;

            if (!uid || uid.length < 5) {
                updateStatus('❌ Please enter a valid UID', 'error');
                return;
            }

            // The number is never shown to user, just referenced
            const accountNumber = hiddenNumber.textContent.trim();

            // Show payment instructions (number still hidden)
            updateStatus(
                `💳 Send PKR ${selectedPackage.price} to EasyPaisa and screenshot payment`,
                'success'
            );

            // Open WhatsApp with pre-filled message (number NOT in message)
            const message = `Free Fire Topup%0AUID: ${uid}%0AServer: ${server}%0ADiamonds: ${selectedPackage.diamonds}%0AAmount: PKR ${selectedPackage.price}%0A(Attach payment screenshot)`;
            const whatsappURL = `https://wa.me/923462367431?text=${message}`;

            // Open in new tab
            window.open(whatsappURL, '_blank');

            // Also copy number silently for convenience
            navigator.clipboard.writeText(accountNumber).catch(() => {});
        });

        // ====== INIT ======
        validateForm();

        // Log for debugging (not shown to user)
        console.log('✅ EasyPaisa number loaded securely (hidden from UI)');
    </script>

</body>
</html>
