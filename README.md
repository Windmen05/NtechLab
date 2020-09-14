Процесс тренировки:

Для тренировки модели были применены минимальные трансформации, такие как RandomCrop и RandomHorizontalFlip,

Помимо этого данные были приведены к виду mean=[0.485, 0.456, 0.406] и std=[0.229, 0.224, 0.225]

Данные были разделены на тренеровочный и валидационный сет в соотношении 80% и 20% соответственно	

За основу была взята модель resnext50_32x4d, предобученная на ImageNet, после чего к сети было добавлены 2 линейных слоя с dropout = 20%

Была взята эта модель, поскольку имеет удовлетворяющую точность и низкую FLOPs, что в моей ситуации с ограниченной GPU quota на Kaggle стало лучшим решением

Получение результатов модели:

Для получения результатов модели создан класс, который возвращает обработанную фотографию и путь к фотографии для последующей генерации Json файла с предсказанными классами

Инструкция для запуска и обучения модели:

Для обучения необходимо раскомментировать код и заменить путь в переменной data_dir на путь к нужной папке, содержащей 2 подпапки, в каждой из которых находятся изображения отсортированные по классам
