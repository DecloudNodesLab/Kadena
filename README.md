<div align="center"> 

<p align="center"><img src="https://user-images.githubusercontent.com/23629420/219872517-2adc32b1-5f64-4d48-9a81-1e2ef6b01a53.png" width=90% </p>

# Нода Kadena в Akash Network

</div>

___

<div align="center">
  
| [Twitter Decloud Nodes Lab](https://twitter.com/NodesLab) | 
|:--:|

| [Akash Network](https://akash.network/) | [Forum Akash Network](https://forum.akash.network/) | [Kadena](http://kadena.io/) |
|:--:|:--:|:--:|
___

Наши новостные каналы и русскоязычная техническая поддержка:

| [Discord Akash Network](https://discord.akash.network/) | [Telegram Akash Network EN](https://t.me/AkashNW) | [Telegram Akash Network RU](https://t.me/akash_ru) | [Twitter Akash Network](https://twitter.com/akashnet_) 
|:--:|:--:|:--:|:--:|
  
  
| [Discord Kadena](https://discord.com/invite/bsUcWmX) | [Telegram Kadena](https://t.me/kadena_io) | [Twitter Kadena](https://twitter.com/kadena_io)
|:--:|:--:|:--:|

| [English guide](/README.md) | 
|:--:|  
</div>

___

## Развертка ноды
Откройте [WEB интерфейс](https://deploy.cloudmos.io/) `Cloudmos`.

Убедитесь, что на вашем балансе есть **более 6 АКТ** и **присутсвует сертификат** (если нет, то обратитесь к [инструкции по использованию Cloudmos](https://github.com/DecloudNodesLab/Guides/blob/main/Russian/Cloudmos.md#%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82%D0%B0-%D0%B8-%D0%BF%D0%BE%D0%B4%D0%B3%D0%BE%D1%82%D0%BE%D0%B2%D0%BA%D0%B0-%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B5)). Далее, нажмите кнопку `DEPLOY`, выберите пустой темплейт `Empty` и скопируйте туда содержимое [deploy.yml]([/deploy.yml](https://raw.githubusercontent.com/DecloudNodesLab/Kadena/main/deploy.yml)).
___

<p align="center"><img src="https://user-images.githubusercontent.com/23629420/223087667-86967145-5557-49ad-ba2c-449d51f284c4.gif" width=70% </p>

___
Нода `Kadena` требует **выделенного IP адреса и статических внешних портов**, для этого необходимо внести небольшие изменения в манифест (deploy.yml),
а именно, замените `your_endpoint_name` в разделах `endpoints` и `expose` на уникальное имя (**только латинские символы нижнего регистра!**)

* `--p2p-hostname=` - при первом разверытвании оставьте пустым.
> Если Вы захотите сменить `LISTEN_PORT` или `REMOTE_PORT` - не забудьте также внести изменения в соответвующих пунктах раздела `EXPOSE`.
Также, для продвинутых пользоветелей, [создан перечень доступных переменных](/VARIABLES.md) с коротким описанием.
  
<p align="center"><img src="https://user-images.githubusercontent.com/23629420/223088770-40ea05f4-7b2e-45ff-b603-c6a6644e4e2a.gif" width=70% </p>

До начала развертывания, мы не можем знать какой **IPv4** адрес нам будет назначен, поэтому мы начнем развертку с пустым `--p2p-hostname`. Мы заполним его, как только получим адрес **IPv4** от провайдера и обновим наш деплой. <br/> 
Пришло время запросить текущие предложения на рынке вычислительных мощностей. Нажимаем `CREATE DEPLOYMENT`, подтверждаем транзакцию (будет заморожено **5 АКТ**) и дожидаемся появления предложений от провайдеров.
  
<br/> 
  
<p align="center"><img src="https://user-images.githubusercontent.com/23629420/223093591-ee9a601b-95c6-491e-99e0-1b6bfc92bc6f.gif" width=70% </p>

<br/> 
  
Количество провайдеров, готовых предоставить вычислительные мощности **с функцией статического IP**, на данный момент ограничено, поэтому возможна ситуация, когда ни один провайдер не отклкнется на ваше предложение.Итак, я выбрал доступного и продолжил разветывание.<br/> 
В логах мы можем увидеть назначенный нам **IPv4** адрес. Он также отображается на владке `LEASES` нашего развертывания.
Все что нам остается - это скопировать его, вставить в наш манифест (deploy.yml) на странице `UPDATE` и обновить развертывание. <br/> 
Обратите внимание на правильность заполнения, данные должны находится ВНУТРИ кавычек, например: <br/> `'--p2p-hostname=YOUR_STATIC_IP_ADDRESS'` <br/>
Вот как это выглядит:

<p align="center"><img src="https://user-images.githubusercontent.com/23629420/223095613-d7c83ce2-583f-48fa-a8d9-9f8a19996e1f.gif" width=70% </p>

Пример корректных рабочих логов:<br/> 
![image](https://user-images.githubusercontent.com/23629420/221644766-0b182d4b-813e-41ef-ab31-22cd55059583.png)<br/> 
В браузере, перейдя по адресу `https://<public-ip>:1789/chainweb/0.0/mainnet01/cut` во можете наблюдать за работой ноды через web сокет. <br/>
На этом установка завершена!<br/> <br/> 
Спасибо что воспользовались **Akash Network**!
