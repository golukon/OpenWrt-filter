# Что это?

Этот проект каждые сутки автоматически генерирует файл GeoIP для использования в VPN или прокси. При этом становится возможным заходить на сервисы, заблокированные для России или внутри России. Скачать geosite.dat можно из других репозиториев (например https://github.com/1andrevich/Re-filter-lists/)

Особенность проекта: отсутствие лишних записей и дублирования в файле, а значит меньший размер по сравнению с другими проектами, что позволяет использовать данный geoip.dat на слабых роутерах (OpenWrt).

Источники данных: [antifilter allyouneed.lst](https://antifilter.download/) и [community.antifilter](https://community.antifilter.download/).

# Категории

- `ru-blocked` содержит список заблокированных ip `allyouneed.lst` сервиса antifilter.download
- `ru-blocked-community` содержит `community.lst` сервиса community.antifilter.download. В нем в основном то, что блокируется извне для России

# Пример конфигурации для v2raya (RoutingA)

```
default: direct
# write your own rules below
ip(geoip:ru-blocked)->proxy
ip(geoip:ru-blocked-community)->proxy
```

# Cкачать

По данному адресу всегда доступна последняя версия файла.

- **geoip.dat**
    - [https://raw.githubusercontent.com/golukon/OpenWrt-filter/release/geoip.dat](https://raw.githubusercontent.com/golukon/OpenWrt-filter/release/geoip.dat)
    - [https://cdn.jsdelivr.net/gh/golukon/OpenWrt-filter@release/geoip.dat](https://cdn.jsdelivr.net/gh/golukon/OpenWrt-filter@release/geoip.dat)

# Спасибки

Данный репозиторий почти полностью основан на [runetfreedom/russia-blocked-geoip](https://github.com/runetfreedom/russia-blocked-geoip) и [Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip)
