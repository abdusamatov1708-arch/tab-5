# tab-5
# ==============================================================================
# DASTUR TAVSIFI:
# Modul 1 takrori uchun kengaytirilgan mukammal kalkulyator.
# Dastur asosiy amallar (+, -, *, /, //, %, **) bilan birga sonning kvadrat ildizini
# hamda sonlarning foizini hisoblay oladi. Xatoliklar aniq matnlar bilan boshqarilgan.
# Natijalar f-string formatida, nuqtadan keyin 2 xona aniqlikda yaxlitlab chiqariladi.
# ==============================================================================

print("=" * 60)
print("              KENGAYTIRILGAN MUKAMMAL KALKULYATOR               ")
print("=" * 60)
print(" Mavjud amallar:")
print("  [ + ] Qo'shish          [ - ] Ayrish          [ * ] Ko'paytirish")
print("  [ / ] Bo'lish           [ //] Butun bo'lish   [ % ] Qoldiqli bo'lish")
print("  [ **] Darajaga ko'tarish[ ildiz ] Kvadrat ildiz [ foiz ] Foiz hisoblash")
print("=" * 60)

# 1. Amalni tanlash
amal = input("Bajarmoqchi bo'lgan amalingizni kiriting: ").strip().lower()

# Tanlangan amal mavjudligini tekshirish
mavjud_amallar = ["+", "-", "*", "/", "//", "%", "**", "ildiz", "foiz"]

if amal not in mavjud_amallar:
    print("❌ XATOLIK: Noto'g'ri amal kiritildi! Iltimos, ro'yxatdagi amallardan birini tanlang.")
else:
    # 2. Amal turiga qarab sonlarni qabul qilish (Kvadrat ildiz uchun faqat 1 ta son kifoya)
    if amal == "ildiz":
        son_matn = input("Ildiz ostidagi sonni kiriting: ").strip()
        
        # Son kiritilganini tekshirish (manfiy sonlar va nuqtalarni inobatga olgan holda)
        if son_matn.replace(".", "", 1).replace("-", "", 1).isdigit():
            son = float(son_matn)
            
            if son < 0:
                print("❌ XATOLIK: Haqiqiy sonlar to'plamida manfiy sonning kvadrat ildizi mavjud emas!")
            else:
                natija = son ** 0.5
                print("-" * 60)
                print(f"√{son} = {natija:.2f}")
        else:
            print("❌ XATOL
