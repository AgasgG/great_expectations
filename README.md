# great_expectations


# ТАБЛИЦА
expect_table_row_count_to_be_between(max_value=1100, min_value=900)
Проверка на кол-во строк. В таблице содержится ~1000 строк, проверка позволяет отловить перепад в 10% изменении. Проверка наполненности.

expect_table_column_count_to_equal(value=8)
Проверка кол-ва столбцов в таблице. Проверка целостности. 

expect_table_columns_to_match_ordered_list(column_list=['user_id', 'pay_doc_type', 'pay_doc_num', 'account', 'phone', 'billing_period', 'pay_date', 'sum'])
Проверка наименований и порядка столбцов в таблице. Проверка целостности. 

# СТОБЕЦ

## pay_doc_type
expect_column_values_to_not_be_null(column='pay_doc_type')
Не должен содержать NULL.

expect_column_kl_divergence_to_be_less_than(column='pay_doc_type', partition_object={'values': ['MASTER', 'MIR', 'VISA'], 'weights': [0.322, 0.343, 0.335]}, threshold=0.45)
Соотношение значений позволит найти проблему если по одной из плат. систем не будет приходить инф-ия. 


expect_column_distinct_values_to_equal_set(column='pay_doc_type', value_set=['MASTER', 'MIR', 'VISA'])
Может принимать только одно из значений из списка. Больше или меньше = аномалия. 

## user_id
expect_column_values_to_not_be_null(column='user_id')
Не должен содержать NULL.

## pay_doc_num
expect_column_values_to_not_be_null(column='pay_doc_num')
Не должен содержать NULL.

## account
expect_column_values_to_not_be_null(column='account')
Не должен содержать NULL.

## phone
expect_column_values_to_not_be_null(column='phone')
Не должен содержать NULL.


expect_column_value_lengths_to_be_between(column='phone', max_value=12, min_value=10)
Длина значения не должна быть меньше 10 символов (901 234 567 8, без пробелов) или больше 12 (+79012345678)

## billing_period
expect_column_values_to_not_be_null(column='billing_period')
Не должен содержать NULL.

expect_column_value_lengths_to_be_between(column='billing_period', max_value=7, min_value=6)
Длина значения не должна быть меньше 6 символов (2012-1) или больше 7 (2012-01)

## pay_date

expect_column_values_to_not_be_null(column='pay_date')
Не должен содержать NULL.


## sum
expect_column_values_to_not_be_null(column='sum')
Не должен содержать NULL.

expect_column_values_to_be_between(column='sum', max_value=None, min_value=1e-07, strict_max=False, strict_min=False)
Значение должно быть больше нуля.
