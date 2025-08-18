# 🕶 Чек-лист: Разделение цифровой жизни («Официальная» и «Псевдонимная»)

Цель: создать две независимые цифровые личности с минимальным риском пересечения.

---

## 📅 День 1. Сетевой фундамент
- [ ] Настроить **два сегмента сети**:
  - [ ] Официальный сегмент → напрямую через статический IP провайдера.
  - [ ] Псевдонимный сегмент → только через каскадный VPN (2 сервера).
- [ ] На псевдонимном сегменте:
  - [ ] Включить **kill-switch** в VPN-клиенте/роутере.
  - [ ] Настроить **DNS только через VPN**.
  - [ ] Полностью отключить **IPv6** (во избежание утечек).

### 🔧 Мини-гайды:
**Выключение IPv6 на Linux (systemd-networkd/NetworkManager):**
```bash
sudo sysctl -w net.ipv6.conf.all.disable_ipv6=1
sudo sysctl -w net.ipv6.conf.default.disable_ipv6=1
echo "net.ipv6.conf.all.disable_ipv6 = 1" | sudo tee -a /etc/sysctl.conf
echo "net.ipv6.conf.default.disable_ipv6 = 1" | sudo tee -a /etc/sysctl.conf
