<section id="order-form" style="padding: 20px; text-align: center;">
    <h2>نموذج الطلب</h2>
    <div style="max-width: 400px; margin: auto; background: #fff; padding: 20px; border-radius: 10px; box-shadow: 0 0 10px rgba(0,0,0,0.1);">
        <input type="text" id="custName" placeholder="الاسم الكامل" style="width: 100%; margin-bottom: 10px; padding: 10px;">
        <select id="prodName" style="width: 100%; margin-bottom: 10px; padding: 10px;">
            <option value="">اختر المنتج</option>
            <option value="المنتج الأول">المنتج الأول</option>
            <option value="المنتج الثاني">المنتج الثاني</option>
        </select>
        <input type="tel" id="custPhone" placeholder="رقم الهاتف" style="width: 100%; margin-bottom: 10px; padding: 10px;">
        <textarea id="custAddress" placeholder="العنوان" style="width: 100%; margin-bottom: 10px; padding: 10px;"></textarea>
        
        <button onclick="sendToWhatsapp()" style="width: 100%; padding: 12px; background: #25d366; color: white; border: none; border-radius: 5px; cursor: pointer; font-weight: bold;">
            إرسال الطلب عبر واتساب
        </button>
    </div>
</section>

<script>
function sendToWhatsapp() {
    // ضع رقم هاتفك هنا بصيغة دولية (مثلاً 212600000000)
    const myNumber = "212715088120"; 
    
    const name = document.getElementById('custName').value;
    const product = document.getElementById('prodName').value;
    const phone = document.getElementById('custPhone').value;
    const address = document.getElementById('custAddress').value;

    if(name == "" || product == "" || phone == "") {
        alert(" المعلومات الأساسية");
        return;
    }

    const message = `طلب جديد من المتجر:%0A` +
                    `الاسم: ${name}%0A` +
                    `المنتج: ${product}%0A` +
                    `الهاتف: ${phone}%0A` +
                    `العنوان: ${address}`;

    window.open(`https://wa.me/${myNumber}?text=${message}`, '_blank');
}
</script>
