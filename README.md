<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wiivon Zambia | Marketplace & Delivery</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        .zambia-gradient { background: linear-gradient(135deg, #007A33 0%, #DE2010 100%); } /* Zambian Flag Colors */
        .card-hover:hover { transform: translateY(-5px); transition: 0.3s; }
    </style>
</head>
<body class="bg-gray-100 font-sans">

    <!-- TOP NAVIGATION -->
    <nav class="zambia-gradient text-white p-4 sticky top-0 z-50 shadow-xl border-b-4 border-yellow-500">
        <div class="container mx-auto flex justify-between items-center">
            <div class="flex items-center space-x-2">
                <span class="text-3xl font-black tracking-tighter italic">WIIVON</span>
                <span class="bg-black text-white text-[10px] px-2 py-1 rounded font-bold uppercase">2% Commission</span>
            </div>
            <div class="hidden md:flex space-x-6 items-center">
                <a href="#" class="hover:text-yellow-400">Services</a>
                <a href="#" class="hover:text-yellow-400">Property Sales</a>
                <a href="#biker-portal" class="bg-black px-4 py-2 rounded-full font-bold text-sm">Biker Portal</a>
                <div class="bg-green-900 px-4 py-2 rounded-lg border border-yellow-600">
                    <i class="fa-solid fa-wallet mr-2"></i>K<span id="userWallet">0.00</span>
                </div>
            </div>
        </div>
    </nav>

    <!-- MAIN DASHBOARD -->
    <main class="container mx-auto py-8 px-4">
        
        <!-- BIKER FLOAT SECTION (Zambian Mobile Money Integration) -->
        <section id="biker-portal" class="mb-10 bg-white rounded-2xl p-6 shadow-sm border border-green-200">
            <div class="flex flex-col md:flex-row justify-between items-center">
                <div>
                    <h2 class="text-2xl font-bold text-gray-800 italic">Biker Fleet Command</h2>
                    <p class="text-gray-500 italic">Maintain your float to receive delivery alerts across Lusaka/Copperbelt.</p>
                </div>
                <div class="text-center mt-4 md:mt-0">
                    <p class="text-sm text-gray-400 uppercase font-bold">Your Float Balance</p>
                    <p id="floatBalanceDisplay" class="text-4xl font-black text-green-700">K0.00</p>
                    <div class="flex gap-2 mt-3">
                        <button onclick="topUpFloat()" class="bg-orange-500 text-white px-4 py-2 rounded-lg font-bold text-xs">
                            Top Up (MTN/Airtel)
                        </button>
                    </div>
                </div>
            </div>
            <div id="floatWarning" class="mt-4 p-3 bg-red-50 text-red-600 rounded-lg text-sm font-medium border border-red-200">
                <i class="fa-solid fa-triangle-exclamation mr-2"></i> Low Float! Top up at least **K50.00** to receive new delivery orders.
            </div>
        </section>

        <!-- CATEGORY GRID -->
        <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mb-10">
            <button class="bg-white p-6 rounded-xl shadow-sm text-center card-hover border-b-4 border-green-600">
                <i class="fa-solid fa-utensils text-3xl text-green-600 mb-2"></i>
                <p class="font-bold">Restaurants</p>
            </button>
            <button class="bg-white p-6 rounded-xl shadow-sm text-center card-hover border-b-4 border-black">
                <i class="fa-solid fa-scale-balanced text-3xl text-black mb-2"></i>
                <p class="font-bold">Law Firms</p>
            </button>
            <button class="bg-white p-6 rounded-xl shadow-sm text-center card-hover border-b-4 border-orange-500">
                <i class="fa-solid fa-tractor text-3xl text-orange-500 mb-2"></i>
                <p class="font-bold">Farms & Land</p>
            </button>
            <button class="bg-white p-6 rounded-xl shadow-sm text-center card-hover border-b-4 border-red-600">
                <i class="fa-solid fa-laptop-code text-3xl text-red-600 mb-2"></i>
                <p class="font-bold">Freelancers</p>
            </button>
        </div>

        <!-- ZAMBIA MARKET LISTINGS -->
        <h3 class="text-2xl font-bold mb-6 italic">Featured on Wiivon Zambia</h3>
        <div class="grid md:grid-cols-3 gap-8">
            
            <!-- Farm Sale -->
            <div class="bg-white rounded-2xl overflow-hidden shadow-md">
                <div class="relative">
                    <img src="https://images.unsplash.com/photo-1500382017468-9049fed747ef?auto=format&fit=crop&w=600&q=80" class="h-48 w-full object-cover">
                    <span class="absolute top-4 right-4 bg-orange-600 text-white px-3 py-1 rounded-full text-xs font-bold uppercase">Land Sale</span>
                </div>
                <div class="p-6">
                    <h4 class="text-xl font-bold uppercase">15 Hectares - Chongwe</h4>
                    <p class="text-gray-500 text-sm mb-4">Title Deed ready, near Great East Road.</p>
                    <div class="flex justify-between items-center">
                        <span class="text-2xl font-black text-gray-900">K450,000</span>
                        <button onclick="buyNow(450000, 'Chongwe Farm')" class="bg-green-700 text-white px-4 py-2 rounded-lg font-bold">Buy Now</button>
                    </div>
                </div>
            </div>

            <!-- Law Firm -->
            <div class="bg-white rounded-2xl overflow-hidden shadow-md">
                <img src="https://images.unsplash.com/photo-1589829545856-d10d557cf95f?auto=format&fit=crop&w=600&q=80" class="h-48 w-full object-cover">
                <div class="p-6">
                    <h4 class="text-xl font-bold uppercase">PACRA Company Setup</h4>
                    <p class="text-gray-500 text-sm mb-4">Lusaka Legal Chambers - Full Doc Upload</p>
                    <div class="flex justify-between items-center">
                        <span class="text-2xl font-black text-gray-900">K2,500</span>
                        <button onclick="buyNow(2500, 'Company Registration')" class="bg-green-700 text-white px-4 py-2 rounded-lg font-bold">Retain</button>
                    </div>
                </div>
            </div>

            <!-- Restaurant Delivery -->
            <div class="bg-white rounded-2xl overflow-hidden shadow-md">
                <img src="https://images.unsplash.com/photo-1513104890138-7c749659a591?auto=format&fit=crop&w=600&q=80" class="h-48 w-full object-cover">
                <div class="p-6">
                    <h4 class="text-xl font-bold uppercase">Village Chicken Platter</h4>
                    <p class="text-gray-500 text-sm mb-4">The Local Kitchen - Rhodes Park</p>
                    <div class="flex justify-between items-center">
                        <span class="text-2xl font-black text-gray-900">K185</span>
                        <button onclick="buyNow(185, 'Village Chicken')" class="bg-green-700 text-white px-4 py-2 rounded-lg font-bold">Order Now</button>
                    </div>
                </div>
            </div>

        </div>
    </main>

    <script>
        let floatBalance = 0.00;
        const commissionRate = 0.02;

        function topUpFloat() {
            let amount = prompt("Enter Amount (K) to deposit into your Biker Float via Airtel/MTN Money:");
            if (amount && !isNaN(amount)) {
                floatBalance += parseFloat(amount);
                updateDisplay();
                alert("Mobile Money Transaction Received! Your float is updated.");
            }
        }

        function updateDisplay() {
            document.getElementById('floatBalanceDisplay').innerText = `K${floatBalance.toFixed(2)}`;
            document.getElementById('userWallet').innerText = floatBalance.toFixed(2);
            const warning = document.getElementById('floatWarning');
            if (floatBalance >= 50) {
                warning.className = "mt-4 p-3 bg-green-50 text-green-600 rounded-lg text-sm font-medium border border-green-200";
                warning.innerHTML = '<i class="fa-solid fa-circle-check mr-2"></i> System Online: New job alerts active for Lusaka.';
            }
        }

        function buyNow(price, item) {
            const comm = price * commissionRate;
            const vendorGets = price - comm;
            
            const confirmPurchase = confirm(`
                WIIVON ZAMBIA - CHECKOUT
                -------------------------
                Service/Item: ${item}
                Price: K${price.toLocaleString()}
                
                Confirm payment via Mobile Money?
            `);

            if(confirmPurchase) {
                alert(`
                    TRANSACTION COMPLETE!
                    
                    Wiivon Commission (2%): K${comm.toLocaleString()}
                    Merchant Receives: K${vendorGets.toLocaleString()}
                    
                    A delivery biker has been notified.
                `);
            }
        }
    </script>
</body>
</html>
