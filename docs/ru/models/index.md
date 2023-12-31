---
comments: true
description: Изучите разнообразные модели семейства YOLO, SAM, MobileSAM, FastSAM, YOLO-NAS и RT-DETR, поддерживаемые Ultralytics. Начните с примеров использования в командной строке и Python.
keywords: Ultralytics, документация, YOLO, SAM, MobileSAM, FastSAM, YOLO-NAS, RT-DETR, модели, архитектуры, Python, CLI
---

# Модели, поддерживаемые Ultralytics

Добро пожаловать в документацию по моделям Ultralytics! Мы поддерживаем широкий спектр моделей, каждая из которых адаптирована для конкретных задач, таких как [обнаружение объектов](../tasks/detect.md), [сегментация на уровне экземпляров](../tasks/segment.md), [классификация изображений](../tasks/classify.md), [оценка позы](../tasks/pose.md) и [множественное отслеживание объектов](../modes/track.md). Если вы заинтересованы в добавлении архитектуры вашей модели в Ultralytics, ознакомьтесь с нашим [Руководством для участников](../../help/contributing.md).

!!! Note

    🚧 Наша многоязычная документация в настоящее время находится в стадии разработки, и мы усердно работаем над ее улучшением. Спасибо за ваше терпение! 🙏

## Основные модели

Вот некоторые ключевые модели, поддерживаемые нами:

1. **[YOLOv3](../../models/yolov3.md)**: Третье поколение семейства моделей YOLO, созданное Джозефом Редмоном, известное своей эффективной способностью обнаружения объектов в реальном времени.
2. **[YOLOv4](../../models/yolov4.md)**: Обновление YOLOv3, оптимизированное для darknet, выпущенное Алексеем Бочковским в 2020 году.
3. **[YOLOv5](../../models/yolov5.md)**: Улучшенная версия архитектуры YOLO от Ultralytics, предлагающая лучшие компромиссы производительности и скорости по сравнению с предыдущими версиями.
4. **[YOLOv6](../../models/yolov6.md)**: Выпущена компанией [Meituan](https://about.meituan.com/) в 2022 году и используется во многих роботах автономной доставки компании.
5. **[YOLOv7](../../models/yolov7.md)**: Обновленные модели YOLO, выпущенные в 2022 году авторами YOLOv4.
6. **[YOLOv8](../../models/yolov8.md)**: Последняя версия семейства YOLO с расширенными возможностями, такими как сегментация на уровне экземпляров, оценка позы/ключевых точек и классификация.
7. **[Segment Anything Model (SAM)](../../models/sam.md)**: Модель Segment Anything от Meta (SAM).
8. **[Mobile Segment Anything Model (MobileSAM)](../../models/mobile-sam.md)**: MobileSAM для мобильных приложений от Университета Кён Хи.
9. **[Fast Segment Anything Model (FastSAM)](../../models/fast-sam.md)**: FastSAM от Группы анализа изображений и видео, Института автоматики, Китайская академия наук.
10. **[YOLO-NAS](../../models/yolo-nas.md)**: Модели YOLO с поиском архитектуры нейронных сетей (NAS).
11. **[Realtime Detection Transformers (RT-DETR)](../../models/rtdetr.md)**: Модели Realtime Detection Transformer (RT-DETR) от Baidu на основе PaddlePaddle.

<p align="center">
  <br>
  <iframe width="720" height="405" src="https://www.youtube.com/embed/MWq1UxqTClU?si=nHAW-lYDzrz68jR0"
    title="YouTube video player" frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen>
  </iframe>
  <br>
  <strong>Смотрите:</strong> Запуск моделей YOLO от Ultralytics всего в несколько строк кода.
</p>

## Начало работы: Примеры использования

!!! Example "Пример"

    === "Python"

        Предварительно обученные модели PyTorch `*.pt` а также файлы конфигурации `*.yaml` могут быть переданы в классы `YOLO()`, `SAM()`, `NAS()` и `RTDETR()` для создания экземпляра модели в Python:

        ```python
        from ultralytics import YOLO

        # Загрузка модели YOLOv8n, предварительно обученной на COCO
        model = YOLO('yolov8n.pt')

        # Отображение информации о модели (необязательно)
        model.info()

        # Обучение модели на примерном наборе данных COCO8 в течение 100 эпох
        results = model.train(data='coco8.yaml', epochs=100, imgsz=640)

        # Запуск использования модели YOLOv8n на изображении 'bus.jpg'
        results = model('path/to/bus.jpg')
        ```

    === "CLI"

        Команды CLI доступны для непосредственного запуска моделей:

        ```bash
        # Загрузка и обучение модели YOLOv8n, предварительно обученной на COCO, на примерном наборе данных COCO8 в течение 100 эпох
        yolo train model=yolov8n.pt data=coco8.yaml epochs=100 imgsz=640

        # Загрузка и запуск использования модели YOLOv8n, предварительно обученной на COCO, на изображении 'bus.jpg'
        yolo predict model=yolov8n.pt source=path/to/bus.jpg
        ```

## Вклад в новые модели

Заинтересованы в добавлении вашей модели в Ultralytics? Замечательно! Мы всегда открыты для расширения нашего портфолио моделей.

1. **Создать форк репозитория**: Начните с создания форка [репозитория Ultralytics на GitHub](https://github.com/ultralytics/ultralytics).

2. **Клонировать ваш форк**: Клонируйте ваш форк на локальный компьютер и создайте новую ветку для работы.

3. **Реализовать вашу модель**: Добавьте вашу модель, следуя стандартам кодирования и руководящим принципам, приведенным в нашем [Руководстве для участников](../../help/contributing.md).

4. **Тщательно протестировать**: Убедитесь, что ваша модель тестируется тщательно как самостоятельно, так и как часть нашего конвейера.

5. **Создать запрос на добавление**: После того, как будете удовлетворены вашей моделью, создайте запрос на добавление в основной репозиторий для рассмотрения.

6. **Код-ревью и слияние**: После рецензирования, если ваша модель соответствует нашим критериям, она будет добавлена в основной репозиторий.

Для более подробных шагов, смотрите наше [Руководство для участников](../../help/contributing.md).
