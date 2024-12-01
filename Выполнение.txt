import os
import pandas as pd


class PriceMachine:

    def load_prices(self, file_path):
        """
        Метод load_prices (Сканирует директорию и ищет файлы со словом price в названии.
        Преобразует файлы к виду: 'наименование', 'цена', 'вес', 'файл', 'цена за кг'.)

        Наименование (название товара) - соответствуют названия: товар, название, наименование, продукт

        Цена (цена товара) - соответствуют названия: розница, цена

        Вес (в кг.) - соответствуют названия: вес, масса, фасовка

        file_path - директория поиска файлов (str)
        new_price - суммарный отсортированный прайс
        """

        file_path = directory
        # создаем пустой файл new_price.csv в который будем скидывать отсортированные прайсы
        new_price = pd.DataFrame(columns=['наименование', 'цена', 'вес', 'файл', 'цена за кг'])
        new_price.to_csv('new_price.csv', index=False)

        for dirpath, dirnames, filenames in os.walk(file_path):
            for file in filenames:
                if (file.find('price') != -1) and (file != 'new_price.csv'):
                    # загружаем данные CSV в DataFrame pandas
                    price = pd.read_csv(file, header=0, delimiter=',')
                    # отфильтровываем данные по условию и преобразовываем к единому стандарту
                    if 'название' in price:
                        if 'цена' in price:
                            if 'вес' in price:
                                price.rename(columns={'название': 'наименование', 'цена': 'цена', 'вес': 'вес'},
                                             inplace=True)
                            elif 'масса' in price:
                                price.rename(columns={'название': 'наименование', 'цена': 'цена', 'масса': 'вес'},
                                             inplace=True)
                            elif 'фасовка' in price:
                                price.rename(columns={'название': 'наименование', 'цена': 'цена', 'фасовка': 'вес'},
                                             inplace=True)
                        elif 'розница' in price:
                            if 'вес' in price:
                                price.rename(columns={'название': 'наименование', 'розница': 'цена', 'вес': 'вес'},
                                             inplace=True)
                            elif 'масса' in price:
                                price.rename(columns={'название': 'наименование', 'розница': 'цена', 'масса': 'вес'},
                                             inplace=True)
                            elif 'фасовка' in price:
                                price.rename(columns={'название': 'наименование', 'розница': 'цена', 'фасовка': 'вес'},
                                             inplace=True)
                    elif 'продукт' in price:
                        if 'цена' in price:
                            if 'вес' in price:
                                price.rename(columns={'продукт': 'наименование', 'цена': 'цена', 'вес': 'вес'},
                                             inplace=True)
                            elif 'масса' in price:
                                price.rename(columns={'продукт': 'наименование', 'цена': 'цена', 'масса': 'вес'},
                                             inplace=True)
                            elif 'фасовка' in price:
                                price.rename(columns={'продукт': 'наименование', 'цена': 'цена', 'фасовка': 'вес'},
                                             inplace=True)
                        elif 'розница' in price:
                            if 'вес' in price:
                                price.rename(columns={'продукт': 'наименование', 'розница': 'цена', 'вес': 'вес'},
                                             inplace=True)
                            elif 'масса' in price:
                                price.rename(columns={'продукт': 'наименование', 'розница': 'цена', 'масса': 'вес'},
                                             inplace=True)
                            elif 'фасовка' in price:
                                price.rename(columns={'продукт': 'наименование', 'розница': 'цена', 'фасовка': 'вес'},
                                             inplace=True)
                    elif 'товар' in price:
                        if 'цена' in price:
                            if 'вес' in price:
                                price.rename(columns={'товар': 'наименование', 'цена': 'цена', 'вес': 'вес'},
                                             inplace=True)
                            elif 'масса' in price:
                                price.rename(columns={'товар': 'наименование', 'цена': 'цена', 'масса': 'вес'},
                                             inplace=True)
                            elif 'фасовка' in price:
                                price.rename(columns={'товар': 'наименование', 'цена': 'цена', 'фасовка': 'вес'},
                                             inplace=True)
                        elif 'розница' in price:
                            if 'вес' in price:
                                price.rename(columns={'товар': 'наименование', 'розница': 'цена', 'вес': 'вес'},
                                             inplace=True)
                            elif 'масса' in price:
                                price.rename(columns={'товар': 'наименование', 'розница': 'цена', 'масса': 'вес'},
                                             inplace=True)
                            elif 'фасовка' in price:
                                price.rename(columns={'товар': 'наименование', 'розница': 'цена', 'фасовка': 'вес'},
                                             inplace=True)
                    elif 'наименование' in price:
                        if 'цена' in price:
                            if 'вес' in price:
                                price.rename(columns={'наименование': 'наименование', 'цена': 'цена', 'вес': 'вес'},
                                             inplace=True)
                            elif 'масса' in price:
                                price.rename(columns={'наименование': 'наименование', 'цена': 'цена', 'масса': 'вес'},
                                             inplace=True)
                            elif 'фасовка' in price:
                                price.rename(columns={'наименование': 'наименование', 'цена': 'цена', 'фасовка': 'вес'},
                                             inplace=True)
                        elif 'розница' in price:
                            if 'вес' in price:
                                price.rename(columns={'наименование': 'наименование', 'розница': 'цена', 'вес': 'вес'},
                                             inplace=True)
                            elif 'масса' in price:
                                price.rename(
                                    columns={'наименование': 'наименование', 'розница': 'цена', 'масса': 'вес'},
                                    inplace=True)
                            elif 'фасовка' in price:
                                price.rename(
                                    columns={'наименование': 'наименование', 'розница': 'цена', 'фасовка': 'вес'},
                                    inplace=True)
                    # Добавляем столбцы
                    price['файл'] = file
                    price['цена за кг'] = (price['цена'] / price['вес']).round(2)
                    # Сохраняем DataFrame в файле new_price.csv, без индексов и заголовков
                    price.to_csv('new_price.csv',
                                 mode='a',
                                 columns=['наименование', 'цена', 'вес', 'файл', 'цена за кг'],
                                 index=False,
                                 header=not os.path.exists('new_price.csv'))
        # загружаем данные new_price.csv в DataFrame new_price игнорируя индекс
        new_price = pd.read_csv('new_price.csv', index_col=None)
        # обновляем индексы
        new_price.reset_index(drop=True, inplace=True)
        # сортируем по наименованию и цене за килограмм
        new_price.sort_values(by=['наименование', 'цена за кг'],
                              ascending=True,
                              inplace=True,
                              ignore_index=True)
        # сохраняем отсортированный DataFrame в файл new_price.csv
        new_price.to_csv('new_price.csv')
        return new_price

    def export_to_html(self, df_name, html_name):
        """
        метод export_to_html выгружает отсортированный DataFrame в html файл
        :param df_name: DataFrame объединяющий все прайсы
        :param html_name: файл в который выводится массив данных в формате html
        :return: метод конвертирует DataFrame в формат HTML-таблицы
        """
        # преобразование df_name в файл html
        df_html = df_name.to_html()
        # сохранение файла
        text_file = open(html_name, "w", encoding='cp1251')
        text_file.write(df_html)
        text_file.close()

    def find_text(self, df_name, text):
        """
        метод find_text получает текст и возвращает список позиций, содержащий этот текст в названии продукта
        :param df_name: DataFrame объединяющий все прайсы
        :param text: текст получаемый от пользователя
        :return filtered_df: список позиций, содержащих текст в названиях продуктов
        """
        filtered_df = df_name[(df_name['наименование'].str.startswith(text))]
        if filtered_df.empty:
            print('Товар не найден! Повторите запрос.')
        else:
            # меняем индексы на порядковый номер
            filtered_df.reset_index(drop=True, inplace=True)
            return filtered_df


if __name__ == '__main__':

    directory = "."
    pm = PriceMachine()
    prs = pm.load_prices(directory)
    print(prs)
    pm.export_to_html(prs, 'output.html')

    # Логика работы программы
    while True:
        # ввод названия товара
        product = input("Введите название товара:  ")
        # если введено название товара
        if not product == 'exit':
            # выводим таблицу найденных товаров
            res = pm.find_text(prs, product)
            print(res)
        # введено слово 'exit'
        else:
            print(f'Работа закончена. До свидания')
            break
