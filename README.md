<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>ЕГЭ Математика: полная теория 1–19 + тесты</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: #f8fafc;
      color: #0f172a;
      line-height: 1.5;
      scroll-behavior: smooth;
    }

    .container {
      max-width: 1400px;
      margin: 0 auto;
      padding: 0 24px;
    }

    /* шапка */
    .header {
      background: white;
      border-bottom: 1px solid #e2e8f0;
      position: sticky;
      top: 0;
      z-index: 100;
      backdrop-filter: blur(4px);
      background: rgba(255,255,255,0.95);
    }

    .header-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      padding: 16px 0;
      gap: 16px;
    }

    .logo h1 {
      font-size: 1.7rem;
      font-weight: 700;
      background: linear-gradient(135deg, #1e3c72, #2b4f8c);
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
    }
    .logo span {
      font-size: 0.85rem;
      color: #475569;
      display: block;
    }

    .nav {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
    }

    .nav-btn {
      background: transparent;
      border: none;
      font-weight: 600;
      padding: 8px 18px;
      border-radius: 40px;
      cursor: pointer;
      transition: all 0.2s;
      font-family: inherit;
      color: #1e293b;
    }

    .nav-btn.active {
      background: #1e3c72;
      color: white;
    }

    .nav-btn:hover:not(.active) {
      background: #eef2ff;
    }

    /* секции */
    .section {
      display: none;
      animation: fade 0.25s ease;
    }

    .section.active-section {
      display: block;
    }

    @keyframes fade {
      from { opacity: 0; transform: translateY(6px);}
      to { opacity: 1; transform: translateY(0);}
    }

    /* теория по задачам */
    .theory-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
      gap: 24px;
      margin: 32px 0;
    }

    .task-card {
      background: white;
      border-radius: 24px;
      padding: 20px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.03);
      border: 1px solid #e2e8f0;
      transition: all 0.2s;
    }
    .task-card:hover {
      transform: translateY(-2px);
      box-shadow: 0 12px 20px -12px rgba(0,0,0,0.1);
    }
    .task-header {
      display: flex;
      align-items: baseline;
      gap: 12px;
      margin-bottom: 16px;
      flex-wrap: wrap;
    }
    .task-num {
      background: #1e3c72;
      color: white;
      padding: 4px 12px;
      border-radius: 40px;
      font-weight: 700;
      font-size: 0.9rem;
    }
    .task-name {
      font-size: 1.3rem;
      font-weight: 700;
      color: #0f172a;
    }
    .task-desc {
      color: #334155;
      margin-bottom: 16px;
      font-size: 0.95rem;
    }
    .formula-block {
      background: #f1f5f9;
      padding: 12px;
      border-radius: 16px;
      font-family: monospace;
      font-size: 0.85rem;
      margin: 12px 0;
      color: #0c4a6e;
    }
    .example {
      background: #fef9e3;
      padding: 10px;
      border-radius: 12px;
      font-size: 0.85rem;
      margin-top: 12px;
      border-left: 3px solid #eab308;
    }

    /* тесты */
    .quiz-card {
      background: white;
      border-radius: 28px;
      padding: 24px;
      margin-bottom: 28px;
      border: 1px solid #e2e8f0;
    }
    .question-text {
      font-size: 1.2rem;
      font-weight: 600;
      margin-bottom: 20px;
    }
    .options {
      display: flex;
      flex-direction: column;
      gap: 12px;
      margin-bottom: 20px;
    }
    .option {
      display: flex;
      align-items: center;
      gap: 12px;
      background: #f8fafc;
      padding: 12px 18px;
      border-radius: 60px;
      border: 1px solid #e2e8f0;
      cursor: pointer;
    }
    .option:hover {
      background: #eef2ff;
    }
    .feedback {
      margin-top: 16px;
      padding: 12px 18px;
      border-radius: 20px;
      font-weight: 500;
    }
    .feedback.correct {
      background: #dcfce7;
      color: #166534;
      border-left: 4px solid #22c55e;
    }
    .feedback.wrong {
      background: #fee2e2;
      color: #991b1b;
      border-left: 4px solid #ef4444;
    }
    .quiz-btn {
      background: #1e3c72;
      color: white;
      border: none;
      padding: 10px 24px;
      border-radius: 40px;
      font-weight: 600;
      cursor: pointer;
    }
    footer {
      margin-top: 64px;
      padding: 28px 0;
      border-top: 1px solid #e2e8f0;
      text-align: center;
      color: #475569;
    }
    @media (max-width: 700px) {
      .theory-grid {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>

<header class="header">
  <div class="container header-inner">
    <div class="logo">
      <h1>MathEge.pro</h1>
      <span>Полная теория | Задания 1–19 (профиль)</span>
    </div>
    <div class="nav">
      <button class="nav-btn active" data-section="theory">📖 Теория 1–19</button>
      <button class="nav-btn" data-section="quiz">📝 Тренировочные тесты</button>
      <button class="nav-btn" data-section="resources">📚 Ресурсы</button>
    </div>
  </div>
</header>

<main class="container">
  <!-- РАЗДЕЛ ТЕОРИЯ: все задачи 1-19 -->
  <section id="theory" class="section active-section">
    <h2 style="font-size: 1.9rem; margin: 20px 0 8px;">📚 Теория по заданиям ЕГЭ (профиль)</h2>
    <p style="margin-bottom: 24px; color: #334155;">Подробный разбор каждой задачи: от простейших уравнений до сложных параметров и экономики.</p>
    <div class="theory-grid" id="tasksGrid"></div>
  </section>

  <!-- ТЕСТЫ -->
  <section id="quiz" class="section">
    <h2 style="font-size: 1.8rem; margin-bottom: 8px;">🧪 Проверь себя</h2>
    <p style="margin-bottom: 28px;">Интерактивные задания по ключевым темам.</p>
    <div id="quiz-container"></div>
  </section>

  <!-- РЕСУРСЫ -->
  <section id="resources" class="section">
    <h2 style="font-size: 1.8rem;">🔗 Полезные ссылки</h2>
    <div class="resources-list" style="margin-top: 24px; display: flex; flex-direction: column; gap: 16px;">
      <div style="background: white; padding: 18px; border-radius: 20px;"><a href="https://fipi.ru/ege" target="_blank">ФИПИ — официальные демоверсии</a><p>Открытый банк заданий, спецификации</p></div>
      <div style="background: white; padding: 18px; border-radius: 20px;"><a href="https://math-ege.sdamgia.ru/" target="_blank">Решу ЕГЭ — генератор вариантов</a><p>Тысячи заданий с решениями</p></div>
      <div style="background: white; padding: 18px; border-radius: 20px;"><a href="https://www.youtube.com/@trushinbv" target="_blank">Трушин Б.В. — разбор 13-19 задач</a><p>Стереометрия, параметры, экономика</p></div>
    </div>
  </section>
</main>

<footer>
  <div class="container">
    <p>📌 Системная подготовка к ЕГЭ по математике: теория + практика. Все материалы актуальны.</p>
  </div>
</footer>

<script>
  // ПОЛНАЯ ТЕОРИЯ для заданий 1–19 (профильный ЕГЭ)
  const tasksTheory = [
    { num: "1", name: "Простейшие уравнения", desc: "Линейные, квадратные, рациональные, иррациональные, показательные, логарифмические.", formulas: "ax + b = 0 → x = -b/a; ax²+bx+c=0 → D = b²-4ac; √(f(x)) = g(x) → f(x)=g²(x) и g(x)≥0.", example: "2ˣ⁺¹ = 8 → 2ˣ⁺¹=2³ → x+1=3 → x=2." },
    { num: "2", name: "Векторы", desc: "Скалярное произведение, координаты, угол между векторами.", formulas: "a·b = x₁x₂+y₁y₂; cosα = (a·b)/(|a||b|); |a| = √(x²+y²).", example: "a(1;2), b(3;4) → a·b=11, |a|=√5, |b|=5 → cosα=11/(5√5)." },
    { num: "3", name: "Стереометрия (куб, призма, пирамида)", desc: "Объемы, площади поверхностей, сечения.", formulas: "Vкуба=a³, Vпризмы=Sосн·h, Vпирамиды=⅓·Sосн·h.", example: "Куб ребро 3 → V=27, Sполн=54." },
    { num: "4", name: "Теория вероятностей", desc: "Классическая вероятность, сложение/умножение событий.", formulas: "P(A)=m/n; P(A∪B)=P(A)+P(B)-P(A∩B).", example: "Бросаем кубик, четное → 3/6=0.5." },
    { num: "5", name: "Простейшие уравнения (тригонометрия)", desc: "sinx=a, cosx=a, tgx=a.", formulas: "sinx=a → x=(-1)ⁿarcsin a+πn; cosx=a → x=±arccos a+2πn.", example: "sinx=½ → x=π/6+2πn, 5π/6+2πn." },
    { num: "6", name: "Планиметрия", desc: "Треугольники, окружности, четырехугольники.", formulas: "Теорема синусов: a/sinA=2R; теорема косинусов: c²=a²+b²-2ab·cosγ.", example: "В прямоугольном треугольнике sinA=прот/гип." },
    { num: "7", name: "Производная и первообразная", desc: "Геометрический смысл, точки экстремума, касательная.", formulas: "f'(x₀)=k; f'(x)=0 → экстремумы; ∫xⁿ dx = xⁿ⁺¹/(n+1)+C.", example: "f(x)=x²-4x → f'(x)=2x-4=0 → x=2 — минимум." },
    { num: "8", name: "Стереометрия (углы и расстояния)", desc: "Угол между прямыми и плоскостями, расстояние от точки до плоскости.", formulas: "sinφ = |(n·v)|/(|n||v|); d = |Ax₀+By₀+Cz₀+D|/√(A²+B²+C²).", example: "Куб: угол между диагональю и плоскостью основания." },
    { num: "9", name: "Преобразование выражений", desc: "Степени, корни, логарифмы, тригонометрия.", formulas: "logₐ(bc)=logₐb+logₐc; a^(logₐb)=b.", example: "log₂8+log₃9=3+2=5." },
    { num: "10", name: "Задачи с прикладным содержанием", desc: "Проценты, округление, физические формулы.", formulas: "S=V·t; проценты: A(1±p/100).", example: "Вклад 10000 под 10% годовых → через год 11000." },
    { num: "11", name: "Графики функций", desc: "Чтение графиков, соответствие функции и производной.", formulas: "Возрастание: f'(x)>0; убывание: f'(x)<0.", example: "По графику производной определить экстремумы." },
    { num: "12", name: "Исследование функций", desc: "Нахождение наибольшего/наименьшего значения на отрезке.", formulas: "Алгоритм: производная, критические точки, значения на концах.", example: "y=x³-3x на [0;2] → min=-2, max=2." },
    { num: "13", name: "Уравнения (сложные)", desc: "Смешанные типы: показательно-степенные, логарифмические с ОДЗ.", formulas: "ОДЗ: аргумент логарифма >0, знаменатель ≠0.", example: "log₂(x-1)=3 → x-1=8 → x=9, ОДЗ x>1." },
    { num: "14", name: "Неравенства", desc: "Рациональные, иррациональные, показательные, логарифмические.", formulas: "Метод интервалов, замена переменной.", example: "(x-2)/(x+3)>0 → (-∞;-3)∪(2;∞)." },
    { num: "15", name: "Экономические задачи", desc: "Вклады, кредиты, оптимизация, аннуитетные платежи.", formulas: "Sₙ = S·(1+r)ⁿ; дифференцированные платежи.", example: "Кредит 1 млн на 12 мес под 10% → ежемесячный платеж." },
    { num: "16", name: "Планиметрия (доказательство)", desc: "Окружности, вписанные/описанные четырехугольники, подобие.", formulas: "Свойство касательной: угол между хордой и касательной.", example: "Доказать, что точки лежат на одной окружности." },
    { num: "17", name: "Задачи с параметрами", desc: "Квадратные уравнения, графический метод, аналитика.", formulas: "ax²+bx+c=0 при a=0 — линейное; D>0, D=0.", example: "Найти все a, при которых уравнение имеет ровно 2 корня." },
    { num: "18", name: "Числа и их свойства", desc: "Целые числа, делимость, простые числа, алгоритмы.", formulas: "НОД, НОК, признаки делимости.", example: "Найти все натуральные n, при которых n²+3n+2 — простое." },
    { num: "19", name: "Олимпиадные задачи", desc: "Комбинаторика, теория чисел, последовательности.", formulas: "Формула суммы n первых членов арифметической прогрессии.", example: "Существует ли бесконечно много простых чисел вида n²+1?" }
  ];

  function renderTheory() {
    const grid = document.getElementById('tasksGrid');
    if(!grid) return;
    grid.innerHTML = '';
    tasksTheory.forEach(t => {
      const card = document.createElement('div');
      card.className = 'task-card';
      card.innerHTML = `
        <div class="task-header">
          <span class="task-num">Задание ${t.num}</span>
          <span class="task-name">${t.name}</span>
        </div>
        <div class="task-desc">${t.desc}</div>
        <div class="formula-block">📐 <strong>Формулы/методы:</strong> ${t.formulas}</div>
        <div class="example">📌 <strong>Пример:</strong> ${t.example}</div>
      `;
      grid.appendChild(card);
    });
  }

  // ТЕСТЫ (10 вопросов по разным заданиям)
  const testBank = [
    { text: "Решите уравнение: 3ˣ⁻² = 27", options: ["5", "4", "3", "2"], correct: "5", explanation: "27=3³ → x-2=3 → x=5" },
    { text: "Найдите скалярное произведение векторов a(2;-3) и b(4;5)", options: ["-7", "7", "23", "-23"], correct: "-7", explanation: "2*4 + (-3)*5 = 8 -15 = -7" },
    { text: "Вероятность выпадения орла при двух подбрасываниях монеты (хотя бы один раз)", options: ["0,25", "0,5", "0,75", "1"], correct: "0,75", explanation: "1 - 0.5*0.5 = 0.75" },
    { text: "Найдите производную функции f(x)=x³-5x²+2", options: ["3x²-10x", "x²-5x", "3x²-5", "3x²+10x"], correct: "3x²-10x", explanation: "f'(x)=3x²-10x" },
    { text: "Объем куба равен 27. Найдите его диагональ", options: ["3√3", "9", "3", "6√3"], correct: "3√3", explanation: "a=3, d=a√3=3√3" },
    { text: "log₅(2x+3)=2", options: ["11", "8", "5", "12"], correct: "11", explanation: "2x+3=25 → 2x=22 → x=11" },
    { text: "Найдите sinα, если cosα=0,6 и 0<α<π/2", options: ["0,4", "0,8", "0,64", "0,36"], correct: "0,8", explanation: "sin²α=1-0,36=0,64 → sinα=0,8" },
    { text: "Точка минимума функции y=x²-6x+5", options: ["3", "2", "4", "5"], correct: "3", explanation: "y'=2x-6=0 → x=3, ветви вверх → минимум" },
    { text: "Вклад 50000 рублей под 10% годовых на 2 года (капитализация). Сумма?", options: ["60500", "60000", "61000", "59500"], correct: "60500", explanation: "50000*(1.1)²=50000*1.21=60500" },
    { text: "Решите неравенство: (x-1)(x+4)≤0", options: ["[-4;1]", "(-∞;-4]∪[1;∞)", "[-1;4]", "(-∞;1]"], correct: "[-4;1]", explanation: "корни -4 и 1, парабола вверх → между корнями" }
  ];

  function renderQuiz() {
    const container = document.getElementById('quiz-container');
    if(!container) return;
    container.innerHTML = '';
    testBank.forEach((q, idx) => {
      const card = document.createElement('div');
      card.className = 'quiz-card';
      card.innerHTML = `
        <div class="question-text">${idx+1}. ${q.text}</div>
        <div class="options" id="options-${idx}">
          ${q.options.map(opt => `
            <label class="option">
              <input type="radio" name="q${idx}" value="${opt}">
              <span>${opt}</span>
            </label>
          `).join('')}
        </div>
        <button class="quiz-btn" data-idx="${idx}">Проверить</button>
        <div class="feedback" id="fb-${idx}" style="display:none;"></div>
      `;
      container.appendChild(card);
    });

    document.querySelectorAll('.quiz-btn').forEach(btn => {
      btn.addEventListener('click', (e) => {
        const idx = parseInt(btn.dataset.idx);
        const selected = document.querySelector(`input[name="q${idx}"]:checked`);
        const fbDiv = document.getElementById(`fb-${idx}`);
        if(!selected) {
          fbDiv.style.display = 'block';
          fbDiv.className = 'feedback wrong';
          fbDiv.innerText = '❌ Выберите вариант ответа!';
          return;
        }
        const isCorrect = selected.value === testBank[idx].correct;
        fbDiv.style.display = 'block';
        if(isCorrect) {
          fbDiv.className = 'feedback correct';
          fbDiv.innerHTML = `✅ Верно! ${testBank[idx].explanation}`;
        } else {
          fbDiv.className = 'feedback wrong';
          fbDiv.innerHTML = `❌ Неверно. Правильный ответ: ${testBank[idx].correct}. ${testBank[idx].explanation}`;
        }
      });
    });
  }

  // навигация
  const sections = {
    theory: document.getElementById('theory'),
    quiz: document.getElementById('quiz'),
    resources: document.getElementById('resources')
  };
  function switchSection(sectionId) {
    Object.keys(sections).forEach(k => sections[k].classList.remove('active-section'));
    sections[sectionId].classList.add('active-section');
    document.querySelectorAll('.nav-btn').forEach(btn => {
      if(btn.dataset.section === sectionId) btn.classList.add('active');
      else btn.classList.remove('active');
    });
    if(sectionId === 'quiz' && document.getElementById('quiz-container').children.length === 0) renderQuiz();
  }
  document.querySelectorAll('.nav-btn').forEach(btn => {
    btn.addEventListener('click', () => switchSection(btn.dataset.section));
  });
  
  renderTheory();
  // если сразу тесты активны (нет) но на всякий
  if(document.getElementById('quiz').classList.contains('active-section')) renderQuiz();
</script>
</body>
</html>
