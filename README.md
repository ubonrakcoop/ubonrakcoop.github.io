<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>โปรแกรมคำนวณเงินกู้ฉุกเฉิน - บริการสมาชิกสหกรณ์</title>
    <!-- Tailwind CSS CDN สำหรับการจัดสไตล์ Modern UI -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Prompt Font จาก Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Prompt:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Prompt', sans-serif;
            background-color: #f4f7fa;
        }
    </style>
</head>
<body class="min-h-screen flex items-center justify-center p-4">

    <!-- Card Container -->
    <div class="w-full max-w-md bg-white rounded-2xl shadow-xl overflow-hidden border border-slate-100">
        
        <!-- Header Section -->
        <div class="bg-gradient-to-r from-blue-900 to-blue-700 p-6 text-white text-center relative">
            <div class="w-12 h-12 bg-white/10 rounded-full flex items-center justify-center mx-auto mb-3 backdrop-blur-sm">
                <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                </svg>
            </div>
            <h1 class="text-xl font-bold tracking-wide">คำนวณเงินกู้ฉุกเฉิน</h1>
            <p class="text-blue-100 text-xs mt-1">บริการประมาณการยอดผ่อนชำระสำหรับสมาชิก</p>
        </div>

        <!-- Form Section -->
        <form id="loanForm" class="p-6 space-y-5" onsubmit="calculateLoan(event)">
            
            <!-- 1. ยอดเงินที่ต้องการกู้ -->
            <div>
                <label for="amount" class="block text-sm font-semibold text-slate-700 mb-1">
                    ยอดเงินที่ต้องการกู้ (บาท) <span class="text-red-500">*</span>
                </label>
                <div class="relative rounded-lg shadow-sm">
                    <input type="number" id="amount" required min="1000" step="500" placeholder="เช่น 50000"
                        class="w-full px-4 py-3 pl-10 border border-slate-300 rounded-xl focus:ring-2 focus:ring-blue-600 focus:border-transparent outline-none transition text-slate-800 font-medium">
                    <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none text-slate-400">
                        ฿
                    </div>
                </div>
            </div>

            <!-- 2. อัตราดอกเบี้ยต่อปี -->
            <div>
                <label for="interest" class="block text-sm font-semibold text-slate-700 mb-1">
                    อัตราดอกเบี้ยต่อปี (%) <span class="text-red-500">*</span>
                </label>
                <div class="relative rounded-lg shadow-sm">
                    <input type="number" id="interest" required min="0.1" step="0.01" placeholder="เช่น 6.50"
                        class="w-full px-4 py-3 pl-10 border border-slate-300 rounded-xl focus:ring-2 focus:ring-blue-600 focus:border-transparent outline-none transition text-slate-800 font-medium">
                    <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none text-slate-400">
                        %
                    </div>
                </div>
            </div>

            <!-- 3. จำนวนงวดที่ต้องการผ่อน -->
            <div>
                <label for="months" class="block text-sm font-semibold text-slate-700 mb-1">
                    จำนวนงวดที่ต้องการผ่อน (เดือน) <span class="text-red-500">*</span>
                </label>
                <div class="relative rounded-lg shadow-sm">
                    <input type="number" id="months" required min="1" max="120" placeholder="เช่น 12"
                        class="w-full px-4 py-3 pl-10 border border-slate-300 rounded-xl focus:ring-2 focus:ring-blue-600 focus:border-transparent outline-none transition text-slate-800 font-medium">
                    <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none text-slate-400">
                        <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 002-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"></path>
                        </svg>
                    </div>
                </div>
            </div>

            <!-- Action Button -->
            <button type="submit"
                class="w-full bg-blue-800 hover:bg-blue-900 text-white font-semibold py-3.5 px-4 rounded-xl shadow-lg hover:shadow-xl transform active:scale-[0.98] transition-all duration-200 flex items-center justify-center gap-2">
                <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 7h6m0 10v-3m-3 3h.01M9 17h.01M9 14h.01M12 14h.01M15 11h.01M12 11h.01M9 11h.01M7 21h10a2 2 0 002-2V5a2 2 0 00-2-2H7a2 2 0 00-2 2v14a2 2 0 002 2z"></path>
                </svg>
                คำนวณยอดผ่อน
            </button>
        </form>

        <!-- Result Display Section -->
        <div id="resultBox" class="hidden mx-6 mb-6 p-5 bg-blue-50/80 border border-blue-200 rounded-xl text-center">
            <span class="text-xs font-semibold uppercase tracking-wider text-blue-700 block mb-1">
                ยอดผ่อนชำระต่อเดือนโดยประมาณ
            </span>
            <div class="text-3xl font-extrabold text-blue-900 my-1" id="monthlyPayment">
                0.00
            </div>
            <span class="text-sm font-medium text-slate-600 mb-3 block">บาท / เดือน</span>

            <!-- Technical Detail Breakdown -->
            <div class="border-t border-blue-200/60 pt-3 mt-3 text-xs text-slate-600 space-y-1 text-left">
                <div class="flex justify-between">
                    <span>วงเงินกู้รวม:</span>
                    <span id="summaryAmount" class="font-semibold text-slate-800">-</span>
                </div>
                <div class="flex justify-between">
                    <span>ดอกเบี้ยรวมประมาณ:</span>
                    <span id="summaryInterest" class="font-semibold text-slate-800">-</span>
                </div>
            </div>

            <!-- Disclaimer -->
            <div class="mt-4 pt-3 border-t border-blue-200/60 text-[11px] text-slate-500 leading-relaxed text-left flex items-start gap-1.5">
                <svg class="w-4 h-4 text-amber-500 flex-shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z"></path>
                </svg>
                <span><strong>หมายเหตุ:</strong> การคำนวณนี้เป็นการประมาณการเบื้องต้นด้วยวิธีลดต้นลดดอก ยอดผ่อนชำระจริงอาจมีการเปลี่ยนแปลงขึ้นอยู่กับเงื่อนไข วันที่เริ่มสัญญา และข้อกำหนดของสหกรณ์</span>
            </div>
        </div>

    </div>

    <!-- JavaScript Calculation Logic -->
    <script>
        function calculateLoan(e) {
            e.preventDefault();

            const principal = parseFloat(document.getElementById('amount').value);
            const annualRate = parseFloat(document.getElementById('interest').value);
            const months = parseInt(document.getElementById('months').value);

            if (isNaN(principal) || isNaN(annualRate) || isNaN(months) || principal <= 0 || months <= 0) {
                alert('กรุณากรอกข้อมูลให้ถูกต้องครบถ้วน');
                return;
            }

            // คำนวณดอกเบี้ยรายเดือน (Reducing Balance Method - Amortization)
            const monthlyRate = (annualRate / 100) / 12;
            let monthlyPayment = 0;

            if (monthlyRate === 0) {
                monthlyPayment = principal / months;
            } else {
                monthlyPayment = (principal * monthlyRate * Math.pow(1 + monthlyRate, months)) / 
                                 (Math.pow(1 + monthlyRate, months) - 1);
            }

            const totalRepayment = monthlyPayment * months;
            const totalInterest = totalRepayment - principal;

            // แสดงผลลัพธ์
            document.getElementById('monthlyPayment').innerText = monthlyPayment.toLocaleString('th-TH', {
                minimumFractionDigits: 2,
                maximumFractionDigits: 2
            });

            document.getElementById('summaryAmount').innerText = principal.toLocaleString('th-TH') + ' บาท';
            document.getElementById('summaryInterest').innerText = totalInterest.toLocaleString('th-TH', {
                minimumFractionDigits: 2,
                maximumFractionDigits: 2
            }) + ' บาท';

            // แสดง Result Box
            const resultBox = document.getElementById('resultBox');
            resultBox.classList.remove('hidden');
            resultBox.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
        }
    </script>
</body>
</html>
