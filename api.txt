api
===

Для работы с API требуется следующее: 

Для получения настроек для экранов: 


1. Методом POST по ссылке: http://api.dicsconsulting.com.ua передается
1.1. MAC адрес устройства ('device_id':"FF:FF:FF:00:00") 
1.2. Тип запрашиваемого контента ('type':"settins")

Пример ответа: 

  1. Успех:
  {content:
  [
  'hashtag':'goodbar',
  'style':'landscape',
  'pattern':
    [
      {
      'pattern_id':'1',
      'pattern_imge':'http://www.ucarecdn.com/d5c2f128-3655-44df-81f7-463628678b3b/',
      'duration':10000
      },
      {
      'pattern_id':'2',
      'pattern_imge':'http://www.ucarecdn.com/d5c2f128-3655-44df-81f7-463628678b3b/',
      'duration':10000
      },
      {
      'pattern_id':'3',
      'pattern_imge':'http://www.ucarecdn.com/d5c2f128-3655-44df-81f7-463628678b3b/',
      'duration':10000
      }
    ],
  'public':
    [
      'weather':{
      'pic_id':'1',
      'temp':20,
      'timestanp':'001290102',
      },
      'traffic':{
      'image':'1',
      'bals':20
      },
     
    ]
  ]
  }
  
  2. Error
  {
  content:'error'
  }
  
Для отправки статистики по экранам:

2. Методом POST по ссылке: http://api.dicsconsulting.com.ua передается
2.1. MAC адрес устройства ('device_id':"FF:FF:FF:00:00") 
2.2. Тип запрашиваемого контента ('type':"statistic")
2.3. Статистика ('data_send': json array)

Пример пакета: 

  {'users':
  [
    {
    'user_id':'991232',
    'source':'instagram',
    'timestamp':'881273123',
    'image':'http://www.ucarecdn.com/d5c2f128-3655-44df-81f7-463628678b3b/',
    'message':'Hello World!'
    },
    {
    'user_id':'3242343',
    'source':'twitter',
    'timestamp':'453452343',
    'image':'http://www.ucarecdn.com/d5c2f128-3655-44df-81f7-463628678b3b/',
    'message':'Hello Everybody!'
    },
  ],
  'pattern':
  [
    {
    'pattern_id':'3',
    'timestamp':'726347632'
    },
    {
    'pattern_id':'23',
    'timestamp':'557634554'
    }
  ]
  }
  
  Пример ответа:
  
  {
  content:'ok'
  }
  
  или
  
  {
  content:'error'
  }
