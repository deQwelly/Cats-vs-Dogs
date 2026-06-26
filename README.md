# Cats vs Dogs Classification

## Описание проекта
Система бинарной классификации изображений (кошки/собаки) на основе сверточных нейронных сетей. Проведено сравнение обучения модели с нуля, fine-tuning и transfer learning.

## Цель
Исследование влияния архитектуры и подхода к обучению на качество классификации при ограниченной настройке гиперпараметров.

## Данные
- Датасет: ImageFolder (PetImages)
- Классы: Cats / Dogs
- Предобработка:
  - фильтрация повреждённых изображений
  - Resize + CenterCrop
- Разбиение:
  - Train / Validation / Test

## Аугментации
- RandomResizedCrop
- RandomHorizontalFlip
- Normalize

## Модели
- Custom CNN (архитектура на основе AlexNet)
- ResNet18:
  - обучение с нуля (fine-tuning)
  - transfer learning (заморозка backbone)

## Обучение
- Optimizer: AdamW
- Loss: CrossEntropyLoss
- Batch size: 128
- Early stopping по validation loss
- Reproducibility: фиксация seed для PyTorch, NumPy и DataLoader

## Результаты
- Custom CNN: стабильное обучение, ограниченная обобщающая способность
- ResNet18 (fine-tuning): улучшение качества по сравнению с CNN
- ResNet18 (transfer learning): лучший результат
- Final test accuracy: **98.2%**

## Стек технологий
- Python
- PyTorch
- torchvision
- NumPy
- Matplotlib
- Weights & Biases

## Вывод
Transfer learning с предварительно обученной ResNet18 показал наилучшее качество и устойчивость на небольшом датасете, значительно превосходя обучение с нуля.
