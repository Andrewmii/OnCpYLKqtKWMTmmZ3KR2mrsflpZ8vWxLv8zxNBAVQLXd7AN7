
<h1 align="center">
  MER-AGCA 
  <br>
</h1>

## Быстрый старт
- Склонируйте репозиторий
```bash
$ git clone https://github.com/Andrewmii/OnCpYLKqtKWMTmmZ3KR2mrsflpZ8vWxLv8zxNBAVQLXd7AN7.git
$ cd OnCpYLKqtKWMTmmZ3KR2mrsflpZ8vWxLv8zxNBAVQLXd7AN7
```
- Создайте виртуальное окружение и установите необходимые зависимости
```bash
$ python3.8 -m venv venv
$ source venv/bin/activate
$ pip install pytorch==2.0.1 torchvision==0.15.2 torchaudio==2.0.2 pytorch-cuda=11.8 
$ pip install -r requirements.txt
```

- Подготовьте набор данных [ESD](https://hltsingapore.github.io/ESD/) для обучения и тестирования модели. 

```bash
$ cd scripts && python preprocess.py -ds ESD --data_root ./data/Emotion\ Speech\ Dataset
```

- Отредактируйте [конфигурационный файл](./src/configs/base.py) и запустите обучение модели.

```bash
$ cd scripts && python train.py -cfg ../src/configs/hubert_base.py
```

- Оцените качество модели на тестовой выборке.

```bash
$ cd scripts && python eval.py -ckpt ../result/MemoCMT_bert_hubert_base/20260417-104655 --data_name ESD --data_root ../scripts/ESD_preprocessed
```

> GitHub [@Andrewmii](https://github.com/Andrewmii)
