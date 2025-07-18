# === ОБЯЗАТЕЛЬНЫЕ ПОЛЯ ===
api_key: "livekit server api key"  # или LIVEKIT_API_KEY env
api_secret: "livekit server api secret"  # или LIVEKIT_API_SECRET env  
ws_url: "livekit server websocket url"  # или LIVEKIT_WS_URL env
redis:
  address: "redis address"  # должен совпадать с livekit server
  username: "redis username"  # опционально
  password: "redis password"  # опционально
  db: 0  # redis db number, опционально

# === ОПЦИОНАЛЬНЫЕ ПОЛЯ ===

# Порты для мониторинга и отладки
health_port: 8080  # HTTP порт для health checks
prometheus_port: 9090  # порт для prometheus метрик
pprof_port: 6060  # порт для pprof отладки

# SIP настройки
sip_port: 5060  # порт для SIP трафика (по умолчанию 5060)
sip_port_listen: 5060  # порт для прослушивания SIP (по умолчанию = sip_port)
sip_hostname: 'sip.example.com'  # hostname для SIP
sip_from_hostname: 'sip.exolve.ru' # hostname для From заголовка SIP
sip_ringing_interval: "1s"  # интервал звонка от 1с до 60с (по умолчанию 1s)

# TLS настройки для SIP
tls:
  port: 5061  # объявляемый TLS порт (по умолчанию 5061)
  port_listen: 5061  # порт для прослушивания TLS (по умолчанию = port)
  certs:
    - cert_file: "/path/to/cert.pem"
      key_file: "/path/to/key.pem"

# RTP настройки
rtp_port:
  start: 10000  # начальный порт для RTP (по умолчанию 10000)
  end: 20000    # конечный порт для RTP (по умолчанию 20000)

# Логирование
logging:
  level: "info"  # debug, info, warn, error (по умолчанию info)
  json: false    # использовать JSON формат логов

# Кластеризация
cluster_id: "cluster1"  # ID кластера для этого экземпляра

# Производительность
max_cpu_utilization: 0.9  # максимальная загрузка CPU (по умолчанию 0.9)

# Сетевые настройки
use_external_ip: false  # использовать внешний IP
local_net: "192.168.0.0/24"  # локальная сеть для использования
nat_1_to_1_ip: "1.2.3.4"  # статический NAT IP
listen_ip: "0.0.0.0"  # IP для прослушивания

# Медиа настройки (если отличаются от signaling IP)
media_use_external_ip: false  # использовать внешний IP для медиа
media_nat_1_to_1_ip: "1.2.3.4"  # статический NAT IP для медиа

# Таймауты медиа
media_timeout: "30s"  # таймаут медиа
media_timeout_initial: "5s"  # начальный таймаут медиа

# Кодеки
codecs:
  "opus": true
  "pcmu": true
  "pcma": false

# Безопасность
hide_inbound_port: false  # скрыть порт от сканеров
add_record_route: false  # добавлять Record-Route заголовки

# DTMF и аудио
audio_dtmf: false  # генерировать аудио DTMF тоны
enable_jitter_buffer: false  # включить jitter buffer
enable_jitter_buffer_prob: 0.1  # вероятность включения jitter buffer