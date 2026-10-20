# Frigate NVR — официальный upstream

Требуется HomeAiCore >=0.1.211. `source.json` — декларация строго разрешённого официального источника, не статический installable manifest.

Core обнаруживает стабильные релизы напрямую в GitHub `blakeblackshear/frigate`, проверяет OCI digest и Linux-архитектуру в GHCR и создаёт Manifest v2, закреплённый на platform digest. Поддерживаемая серия адаптера: >=0.18.2 <0.19.0. Новые minor/major версии не разрешаются автоматически.

Каталог не задаёт произвольные URL, команды, mounts, ports или permissions. Frigate устанавливается отдельным модулем, не заменяя NVR/Home Assistant. Выбор версии и digest подтверждается вручную. Кэш/stale-данные не используются как разрешение на установку.

В Core реализованы native UI/API bridge, фиксированный CPU Docker-профиль без опубликованных портов/GPU/USB, health-check, проверенная копия конфигурации и SQLite, rollback и восстановление прерванного обновления. Полная документация: `home-ai-core/docs/integrations/frigate.md`.

Старые версии Core игнорируют поле upstreams; устанавливать официальный контейнер как обычный generic /data-модуль нельзя.
