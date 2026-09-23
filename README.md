<div style="font-family: 'Prompt', 'Sarabun', 'Segoe UI', -apple-system, BlinkMacSystemFont, sans-serif; max-width: 480px; margin: 20px auto; background-color: #ffffff; border-radius: 16px; box-shadow: 0 10px 25px -5px rgba(15, 23, 42, 0.1), 0 8px 10px -6px rgba(15, 23, 42, 0.05); border: 1px solid #e2e8f0; overflow: hidden; color: #1e293b; box-sizing: border-box;">

  <!-- Header Banner -->
  <div style="background: linear-gradient(135deg, #0f172a 0%, #1e3a8a 60%, #1d4ed8 100%); padding: 24px 20px; text-align: center; color: #ffffff;">
    <div style="width: 48px; height: 48px; background-color: rgba(255, 255, 255, 0.12); border-radius: 50%; margin: 0 auto 12px auto; display: flex; align-items: center; justify-content: center;">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="#ffffff" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <rect x="2" y="6" width="20" height="12" rx="2"></rect>
        <circle cx="12" cy="12" r="2"></circle>
        <path d="M6 12h.01M18 12h.01"></path>
      </svg>
    </div>
    <h2 style="margin: 0; font-size: 20px; font-weight: 700; letter-spacing: 0.3px; color: #ffffff;">โปรแกรมคำนวณเงินกู้ฉุกเฉิน</h2>
    <p style="margin: 6px 0 0 0; font-size: 13px; color: #93c5fd; font-weight: 300;">ระบบประมาณการยอดผ่อนชำระสำหรับสมาชิกสหกรณ์</p>
  </div>

  <!-- Form Body -->
  <form action="" onsubmit="return false;" style="padding: 24px; margin: 0;">
    
    <!-- Field 1: Amount -->
    <div style="margin-bottom: 18px;">
      <label style="display: block; font-size: 13px; font-weight: 600; color: #334155; margin-bottom: 6px;">
        1. ยอดเงินที่ต้องการกู้ (บาท) <span style="color: #ef4444;">*</span>
      </label>
      <div style="position: relative;">
        <span style="position: absolute; left: 14px; top: 50%; transform: translateY(-50%); color: #64748b; font-weight: 600; font-size: 15px;">฿</span>
        <input type="number" placeholder="เช่น 50000" min="1000" step="500" required style="width: 100%; padding: 12px 14px 12px 36px; border: 1.5px solid #cbd5e1; border-radius: 10px; font-size: 15px; font-weight: 500; color: #0f172a; outline: none; box-sizing: border-box; background-color: #f8fafc;" />
      </div>
    </div>

    <!-- Field 2: Interest -->
    <div style="margin-bottom: 18px;">
      <label style="display: block; font-size: 13px; font-weight: 600; color: #334155; margin-bottom: 6px;">
        2. อัตราดอกเบี้ยต่อปี (%) <span style="color: #ef4444;">*</span>
      </label>
      <div style="position: relative;">
        <span style="position: absolute; left: 14px; top: 50%; transform: translateY(-50%); color: #64748b; font-weight: 600; font-size: 14px;">%</span>
        <input type="number" placeholder="เช่น 6.50" min="0.01" step="0.01" required style="width: 100%; padding: 12px 14px 12px 36px; border: 1.5px solid #cbd5e1; border-radius: 10px; font-size: 15px; font-weight: 500; color: #0f172a; outline: none; box-sizing: border-box; background-color: #f8fafc;" />
      </div>
    </div>

    <!-- Field 3: Months -->
    <div style="margin-bottom: 22px;">
      <label style="display: block; font-size: 13px; font-weight: 600; color: #334155; margin-bottom: 6px;">
        3. จำนวนงวดที่ต้องการผ่อน (เดือน) <span style="color: #ef4444;">*</span>
      </label>
      <div style="position: relative;">
        <span style="position: absolute; left: 14px; top: 50%; transform: translateY(-50%); color: #64748b; font-size: 14px;">📅</span>
        <input type="number" placeholder="เช่น 12" min="1" max="120" required style="width: 100%; padding: 12px 14px 12px 38px; border: 1.5px solid #cbd5e1; border-radius: 10px; font-size: 15px; font-weight: 500; color: #0f172a; outline: none; box-sizing: border-box; background-color: #f8fafc;" />
      </div>
    </div>

    <!-- Submit Button -->
    <button type="submit" style="width: 100%; background: linear-gradient(135deg, #1e3a8a 0%, #1d4ed8 100%); color: #ffffff; border: none; padding: 14px; border-radius: 10px; font-size: 15px; font-weight: 600; cursor: pointer; text-align: center; box-shadow: 0 4px 12px rgba(29, 78, 216, 0.25); display: flex; align-items: center; justify-content: center; gap: 8px;">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#ffffff" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round">
        <path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path>
        <rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect>
      </svg>
      คำนวณยอดผ่อน
    </button>
  </form>

  <!-- Result Display Box -->
  <div style="margin: 0 24px 24px 24px; padding: 20px; background-color: #eff6ff; border: 1.5px dashed #93c5fd; border-radius: 12px; text-align: center;">
    <span style="font-size: 12px; font-weight: 700; color: #1e40af; text-transform: uppercase; letter-spacing: 0.5px; display: block; margin-bottom: 6px;">
      ยอดผ่อนชำระต่อเดือนโดยประมาณ
    </span>
    
    <div style="font-size: 32px; font-weight: 800; color: #1e3a8a; line-height: 1.2; margin: 4px 0;">
      0.00 <span style="font-size: 14px; font-weight: 500; color: #475569;">บาท / เดือน</span>
    </div>

    <!-- Disclaimer -->
    <div style="margin-top: 14px; padding-top: 12px; border-top: 1px solid #dbeafe; font-size: 11px; color: #64748b; line-height: 1.6; text-align: left; display: flex; align-items: flex-start; gap: 6px;">
      <span style="color: #f59e0b; font-size: 14px; line-height: 1;">⚠️</span>
      <span><strong>ข้อระบุสำคัญ:</strong> การคำนวณนี้เป็นการประมาณการเบื้องต้นเท่านั้น ยอดผ่อนชำระจริงอาจมีการเปลี่ยนแปลงตามวันทำสัญญา เงื่อนไขดอกเบี้ยลดต้นลดดอก และข้อกำหนดอย่างเป็นทางการของสหกรณ์</span>
    </div>
  </div>

  <!-- Footer -->
  <div style="background-color: #f8fafc; padding: 12px 20px; border-top: 1px solid #f1f5f9; text-align: center; font-size: 11px; color: #94a3b8;">
    ระบบบริการสมาชิกสหกรณ์ออมทรัพย์ (Member Portal Prototype)
  </div>

</div>
