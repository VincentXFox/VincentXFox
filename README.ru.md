<div align="center">
  <img src="assets/avatar.png" width="140" alt="Vincent Fox Vibe-Junior" />
  <h1>Винсент&nbsp;Фокс</h1>
  <p><b>инструменты для агентов · свой хостинг · фулстек</b><br/>
  <sub>TypeScript · Python · Kotlin</sub></p>
  <sub><a href="README.md">English</a> · <b>Русский</b></sub>
</div>

```console
$ whoami
винсент — делаю инструменты, которыми управляю парком кодирующих агентов с телефона,
и сам держу все сервисы, на которых эти инструменты работают.

$ systemctl status homelab --no-pager
● homelab.target - active (running), 24/7
   узлы     thor1   мини-ПК · Ubuntu 24.04 · агенты, шлюз, панели терминалов
            srv78   VPS     · Debian      · nginx-край, релей, RustDesk, туннели
            de5     край    · терминатор туннеля для адреса телефона
            bigpc   5700X + RTX 3070 · llama.cpp, локальные модели
   связи    WireGuard · ZeroTier · реверс-SSH юниты (сами поднимаются, BatchMode)
   край     nginx SNI-роутинг → anytls · naive · hysteria2 с port hopping
   память   банки Mnemopi + граф проекта, у каждого утверждения есть источник

$ tail -n 2 /var/log/focus.log
  пульт агентов для телефона: шлюз на Bun, PWA на React, движок обновлений с откатом
  правило: «готово» значит проверено настоящим прогоном, а не правдоподобным отчётом
```

## Что строю

| проект | что это |
|---|---|
| **OMP Pocket** <sub>`приватный`</sub> | Пульт для парка агентов [omp](https://www.npmjs.com/package/oh-my-pi) с телефона. PWA на React + шлюз на Bun (реестр сессий, вложения, поиск, пуши, автономные задачи); E2E-релей совместимости на AES-256-GCM; рантайм панелей терминалов с эмуляцией экрана и восстановлением после рестарта; движок обновлений, который проверяет SHA-256, ставит атомарно и сам откатывается, плюс chaos-набор на сценарии отказов. 42 тысячи строк TypeScript (52 с учётом стилей), 30 тестовых файлов. |
| **my-cinema** <sub>`приватный`</sub> | Клиент для Android TV на Kotlin — модульный Gradle (core / feature / app), свой слой дизайна, бенчмарки до работы над фичами. |
| **фид каталога** <sub>`приватный`</sub> | Python: каталог на 2 161 товар обойдён, отфильтрован и собран в строгий YML-фид для Яндекс Директа — цена, наличие, категория и минимум четыре фото на белом фоне у товара; плюс отчёт отбора, где назван повод отсева каждого товара. |
| **домашний хостинг** | VPS на Debian + мини-ПК на Ubuntu: nginx-край со SNI-роутингом, юниты systemd, mesh на WireGuard/ZeroTier, свой RustDesk, llama.cpp с локальными моделями для агентов. |

## Стек

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Bun](https://img.shields.io/badge/Bun-000000?style=flat-square&logo=bun&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)
![Debian](https://img.shields.io/badge/Debian-A81D33?style=flat-square&logo=debian&logoColor=white)
![nginx](https://img.shields.io/badge/nginx-009639?style=flat-square&logo=nginx&logoColor=white)
![systemd](https://img.shields.io/badge/systemd-333333?style=flat-square&logo=systemd&logoColor=white)
![WireGuard](https://img.shields.io/badge/WireGuard-88171A?style=flat-square&logo=wireguard&logoColor=white)
![Caddy](https://img.shields.io/badge/Caddy-1F88C0?style=flat-square&logo=caddy&logoColor=white)
![llama.cpp](https://img.shields.io/badge/llama.cpp-GGUF-black?style=flat-square)

## Сейчас

- **OMP Pocket** — дерево процессов (`WORKFLOW.md` → шаги → подзадачи) и граф памяти, чтобы агент хранил источники того, что утверждает.
- **Правила, которые кусаются** — хуки, а не абзацы: без плана нет правок, без настоящего прогона нет строки статуса, третий одинаковый провал обрывает цикл.

<sub>Всё построено так, чтобы читаться через полгода: без слоёв совместимости, «временных» прослоек и мёртвых веток.</sub>
