
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>MYXAMET SHOP</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background-color: #0d0d0d;
      color: #fff;
    }
    .neon-text {
      color: #ff1f1f;
      text-shadow: 0 0 5px #ff1f1f, 0 0 10px #ff1f1f;
    }
    .neon-box {
      border: 2px solid #ff1f1f;
      box-shadow: 0 0 10px #ff1f1f, 0 0 20px #ff1f1f;
    }
    .shop-btn {
      background-color: #ff1f1f;
      color: #000;
    }
    .shop-btn:hover {
      background-color: #ff4d4d;
    }
  </style>
</head>
<body>

<!-- Выбор страны и валюты -->
<div id="country-currency-selection" class="fixed inset-0 bg-black bg-opacity-90 flex items-center justify-center z-50">
  <div class="bg-gray-900 p-8 rounded-xl neon-box max-w-md w-full text-center">
    <h2 class="text-2xl mb-4 neon-text">Выберите страну и валюту</h2>
    <form id="selectionForm" class="space-y-4">
      <div>
        <label class="block mb-1">Страна:</label>
        <select id="country" name="country" class="w-full p-2 rounded bg-gray-700 text-white">
          <option value="RUB">🇷🇺 Россия</option>
          <option value="KZT">🇰🇿 Казахстан</option>
          <option value="KGS">🇰🇬 Кыргызстан</option>
          <option value="AMD">🇦🇲 Армения</option>
          <option value="AZN">🇦🇿 Азербайджан</option>
          <option value="BYN">🇧🇾 Беларусь</option>
          <option value="GEL">🇬🇪 Грузия</option>
          <option value="UZS">🇺🇿 Узбекистан</option>
          <option value="TJS">🇹🇯 Таджикистан</option>
          <option value="TMT">🇹🇲 Туркменистан</option>
          <option value="TRY">🇹🇷 Турция</option>
          <option value="UAH">🇺🇦 Украина</option>
          <option value="MNT">🇲🇳 Монголия</option>
        </select>
      </div>
      <div>
        <label class="block mb-1">Валюта:</label>
        <select id="currency" name="currency" class="w-full p-2 rounded bg-gray-700 text-white">
          <option value="RUB">₽ Рубль (RUB)</option>
          <option value="KZT">₸ Тенге (KZT)</option>
          <option value="KGS">с Сом (KGS)</option>
          <option value="AMD">֏ Драм (AMD)</option>
          <option value="AZN">₼ Манат (AZN)</option>
          <option value="BYN">Br Белорусский рубль (BYN)</option>
          <option value="GEL">₾ Лари (GEL)</option>
          <option value="UZS">сум Сум (UZS)</option>
          <option value="TJS">ЅМ Сомони (TJS)</option>
          <option value="TMT">m Манат (TMT)</option>
          <option value="TRY">₺ Лира (TRY)</option>
          <option value="UAH">₴ Гривна (UAH)</option>
          <option value="MNT">₮ Тугрик (MNT)</option>
          <option value="USD">$ Доллар (USD)</option>
        </select>
      </div>
      <button type="submit" class="w-full py-2 bg-red-500 hover:bg-red-400 text-black rounded">Продолжить</button>
    </form>
  </div>
</div>

<script>
  document.getElementById('selectionForm').addEventListener('submit', function(e) {
    e.preventDefault();
    const currency = document.getElementById('currency').value;
    if (currency === "KGS") {
      window.location.href = "https://t.me/muhichshopff_bot";
    } else {
      document.getElementById('country-currency-selection').style.display = 'none';
    }
  });
</script>

<header class="text-center py-6">
  <h1 class="text-4xl neon-text font-bold">MYXAMET SHOP</h1>
</header>

<div class="flex justify-center px-4">
  <img src="banner.png" alt="Shop Banner" style="max-width: 800px; width: 100%; border-radius: 12px;" />
</div>

<main class="max-w-6xl mx-auto p-6 grid grid-cols-1 md:grid-cols-3 gap-6 mt-10">
  <div onclick="openModal('Алмазы')" class="cursor-pointer bg-black neon-box rounded-xl p-6 text-center">
    <h2 class="text-2xl neon-text mb-2">Алмазы</h2>
    <p class="mb-4">Пополнение до 50,000 алмазов</p>
    <button class="shop-btn px-6 py-2 rounded">Купить</button>
  </div>
  <div onclick="openModal('Ваучеры')" class="cursor-pointer bg-black neon-box rounded-xl p-6 text-center">
    <h2 class="text-2xl neon-text mb-2">Ваучеры</h2>
    <p class="mb-4">Элитный пропуск и скины</p>
    <button class="shop-btn px-6 py-2 rounded">Купить</button>
  </div>
  <div onclick="openModal('Прокачка')" class="cursor-pointer bg-black neon-box rounded-xl p-6 text-center">
    <h2 class="text-2xl neon-text mb-2">Прокачка</h2>
    <p class="mb-4">Помощь с рангами</p>
    <button class="shop-btn px-6 py-2 rounded">Купить</button>
  </div>
</main>

<!-- Модальное окно -->
<div id="modal" class="fixed inset-0 bg-black bg-opacity-80 flex items-center justify-center hidden z-50">
  <div class="bg-gray-900 p-6 rounded-xl max-w-md w-full border border-red-400">
    <h2 class="text-xl mb-4 neon-text">Оформление заказа</h2>
    <form action="https://formspree.io/f/meokqodv" method="POST" class="space-y-4">
      <input type="hidden" id="productField" name="Продукт" value="">
      <label>ID аккаунта Free Fire:</label>
      <input name="ID аккаунта" required type="text" class="w-full p-2 rounded bg-gray-700 text-white" placeholder="123456789" />
      <label>Способ оплаты:</label>
      <select name="Оплата" required class="w-full p-2 rounded bg-gray-700 text-white">
        <option>Банковская карта</option>
        <option>СБП</option>
        <option>QIWI</option>
        <option>ЮMoney</option>
        <option>Kaspi.kz</option>
        <option>O!Деньги / Элсом</option>
        <option>Crypto</option>
      </select>
      <button type="submit" class="w-full py-2 bg-red-500 hover:bg-red-400 text-black rounded">Отправить заказ</button>
      <button type="button" onclick="closeModal()" class="w-full mt-2 py-2 bg-gray-700 hover:bg-gray-600 text-white rounded">Отмена</button>
    </form>
  </div>
</div>

<script>
  function openModal(product) {
    document.getElementById('productField').value = product;
    document.getElementById('modal').classList.remove('hidden');
  }
  function closeModal() {
    document.getElementById('modal').classList.add('hidden');
  }
</script>

<section class="max-w-3xl mx-auto mt-12 p-6 bg-black neon-box rounded-xl text-center">
  <h3 class="text-3xl neon-text mb-4">📞 Контакты</h3>
  <p class="text-lg mb-2">Telegram: <a href="https://t.me/tologonov_m" class="text-red-400">@tologonov_m</a></p>
  <p class="text-lg">Email: <a href="mailto:fasterff2021@gmail.com" class="text-red-400">fasterff2021@gmail.com</a></p>
</section>

<footer class="text-center mt-12 py-6 text-sm text-gray-500">
  &copy; 2025 MYXAMET SHOP. Все права защищены.
</footer>

</body>
</html>
