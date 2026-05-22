# Hidden-Markov-Models--vol-IMOEX
Modeling Volatility Regimes in the Russian Stock Market with Hidden Markov Models // Моделирование скрытых состояний российского фондового рынка методами скрытых марковских моделей

# MOEX HMM Volatility Regimes

**For English version — scroll down 🇬🇧**

## 🇷🇺 Идея проекта

Фондовый рынок не всегда ведет себя одинаково. Бывают спокойные периоды, бывают фазы повышенной неопределенности, а иногда рынок переходит в стрессовый режим.
<img width="1243" height="620" alt="image" src="https://github.com/user-attachments/assets/20e04f74-7e1b-41c0-9a08-cebf36928969" />
В этом проекте я использовал **Hidden Markov Model (HMM)**, чтобы автоматически выделить скрытые режимы волатильности российского фондового рынка на примере индекса IMOEX.

Главная идея:

> не предсказывать точное значение индекса, а определить, в каком режиме находится рынок сейчас и какой режим наиболее вероятен завтра.


## Экономический смысл

Обычная модель часто предполагает, что рынок описывается одним общим распределением. Но на практике рынок ведет себя по-разному в разные периоды.

HMM позволяет представить рынок как процесс переключения между несколькими состояниями:

| Режим | Экономический смысл |
|---|---|
| Низкая волатильность | спокойный рынок |
| Умеренная волатильность | обычные рыночные колебания |
| Повышенная волатильность | рост неопределенности |
| Высокая волатильность / стресс | нестабильный рынок |

Такой подход помогает не просто смотреть на доходность за один день, а понимать **контекст**, в котором находится рынок.

---

## Главная визуализация

<img width="1248" height="543" alt="image" src="https://github.com/user-attachments/assets/9f8d81e3-e97b-4fde-867b-539ddca46e21" />


На графике видно, как HMM распределяет разные периоды индекса МосБиржи по режимам волатильности.  
Спокойные участки чаще относятся к режиму низкой волатильности, а периоды резких движений рынка — к режимам повышенной и высокой волатильности.

---

## Почему это полезно

HMM можно использовать как дополнительный аналитический признак, то есть как **feature** для других моделей.

Например, в дальнейшем режим HMM можно добавить в:

- модель прогнозирования волатильности;
- модель оценки рыночного риска;
- торговую стратегию;
- скоринговую систему рыночной нестабильности;
- ML-модель для прогноза доходности или риска.

Идея в том, что HMM превращает сложную динамику рынка в понятный признак:

```text
Сегодня рынок в режиме низкой / умеренной / повышенной / высокой волатильности

```
Проверка результата

Модель показала, что режимы обладают устойчивостью и могут использоваться для оценки состояния рынка на следующий день.

Основные результаты:

Метрика	Значение
One-step-ahead accuracy режима	97.70%
Baseline accuracy	38.35%
ROC-AUC для риска высокой волатильности	0.686

Экономический вывод:

HMM хорошо подходит для определения текущего режима рынка и ранжирования будущего риска волатильности.

При этом модель не стоит воспринимать как точный прогноз цены или точную вероятность в процентах. Она полезнее как инструмент мониторинга режима рынка и как дополнительный признак для дальнейшего моделирования.

## 🇬🇧 Project idea

The stock market does not behave the same way all the time. There are calm periods, phases of higher uncertainty, and sometimes the market moves into a stress regime.

<img width="1243" height="620" alt="image" src="https://github.com/user-attachments/assets/20e04f74-7e1b-41c0-9a08-cebf36928969" />

In this project, I used a **Hidden Markov Model (HMM)** to automatically identify hidden volatility regimes in the Russian stock market using the IMOEX index.

The main idea:

> not to predict the exact index value, but to understand which market regime we are in now and which regime is most likely tomorrow.

---

## Economic interpretation

A simple model often assumes that the market is described by one common distribution. In practice, however, the market behaves differently across different periods.

HMM represents the market as a process that switches between several states:

| Regime | Economic meaning |
|---|---|
| Low volatility | calm market |
| Moderate volatility | normal market fluctuations |
| Elevated volatility | growing uncertainty |
| High volatility / stress | unstable market conditions |

This approach helps us look not only at a single daily return, but also at the broader **market context**.

---

## Main visualization

<img width="1248" height="543" alt="image" src="https://github.com/user-attachments/assets/9f8d81e3-e97b-4fde-867b-539ddca46e21" />

The chart shows how HMM assigns different periods of the MOEX Index to volatility regimes.  
Calm periods are more often classified as low-volatility regimes, while periods of sharp market moves are assigned to elevated or high-volatility regimes.

---

## Why this is useful

HMM can be used as an additional analytical feature for other models.

For example, the HMM regime can later be added to:

- a volatility forecasting model;
- a market risk assessment model;
- a trading strategy;
- a market stress scoring system;
- an ML model for return or risk prediction.

The idea is that HMM transforms complex market dynamics into a simple and interpretable feature:

```text
Today the market is in a low / moderate / elevated / high volatility regime
```
esult validation

The model showed that the regimes are stable and can be used to estimate the market state for the next trading day.

Main results:

Metric	Value
One-step-ahead regime accuracy	97.70%
Baseline accuracy	38.35%
ROC-AUC for high-volatility risk	0.686

Economic takeaway:

HMM is useful for identifying the current market regime and ranking future volatility risk.

At the same time, the model should not be treated as an exact price forecast or as a perfectly calibrated probability forecast. It is more useful as a market regime monitoring tool and as an additional feature for further modeling.
