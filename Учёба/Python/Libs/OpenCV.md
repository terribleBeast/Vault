## Основа  
* imgread - чтение изображения
	IMREAD_GRAYSCALE - чб формат
	IMREAD_COLORS - цветной 
* imshow - показать 
* waitKey - ожидание нажатия клавиши (0 - для любой)
* imwrite - сохранения файла

## Пиксели

img.shape(hight, weight, count_channel)
OpenCV хранит их в порядке синего, зеленого и красного цветов:
``` python
img[0, 0] = (255, 0, 0)
(b, g, r) = img[0, 0]
print("Красный: {}, Зелёный: {}, Синий: {}".format(r, g, b))
```****