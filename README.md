<div align="center">

# Disable USB Scan and Fix Dialog Windows 11

**Keep AutoPlay. Skip unwanted disk repair prompts.**

![Windows 11](https://img.shields.io/badge/Windows-11-0078D4?logo=windows&logoColor=white)
![Windhawk](https://img.shields.io/badge/Windhawk-Mod-5856D6)
![Version](https://img.shields.io/badge/version-1.1-blue)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?logo=cplusplus&logoColor=white)
[![MIT License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

[English](#english) · [Русский](#русский) · [Source code](disable-usb-scan-fix.wh.cpp) · [Windhawk submission #7943](https://github.com/ramensoftware/windhawk-mods/pull/7943)

</div>

---

## English

A lightweight [Windhawk](https://windhawk.net/) mod for Windows 11 that suppresses the USB drive scan-and-repair dialog and its associated AutoPlay notification without disabling the AutoPlay service.

### Features

| Feature | Behavior |
| --- | --- |
| Scan and Fix dialog | Automatically selects **Continue without scanning** for matching dialogs |
| Disk repair notification | Suppresses matching disk warning toasts |
| Other notifications | Non-matching notifications are passed through |
| AutoPlay | The service remains enabled |
| Registry | No registry changes |
| Languages | English and Russian warning text |

### Installation

The mod has been submitted to the official Windhawk catalog. Follow the [submission and review status](https://github.com/ramensoftware/windhawk-mods/pull/7943).

To try the source locally before catalog publication:

1. Install [Windhawk](https://windhawk.net/).
2. Open Settings and enable Developer Mode.
3. On the home page, select Create a New Mod.
4. Replace the example code with the complete contents of [disable-usb-scan-fix.wh.cpp](disable-usb-scan-fix.wh.cpp).
5. Compile the mod, enable it and exit editing mode.
6. Safely reconnect the USB drive to test the behavior.

To undo the change, disable the mod in Windhawk.

### Compatibility and implementation

- Target operating system: Windows 11.
- Version 1.1 was compiled and tested on the author's Windows installation. Both hooks initialized successfully; the notification hook logged a blocked warning and neither warning nor dialog appeared.
- Other Windows builds, language configurations, and independent dialog interception have not been fully verified.
- Uses `TaskDialogIndirect` and `IToastNotifier::Show` hooks in the configured processes. Warning text is matched in English or Russian. Unrecognized content is passed through.

> [!WARNING]
> This mod hides warnings. It does not repair filesystem errors, clear the dirty bit, or prevent data loss. Back up important files, eject removable drives safely, and check damaged drives manually when necessary.

---

## Русский

Модификация [Windhawk](https://windhawk.net/) для Windows 11, которая скрывает окно проверки и исправления USB-накопителя и связанное уведомление автозапуска, не отключая службу автозапуска.

### Возможности

| Функция | Действие |
| --- | --- |
| Окно проверки диска | Автоматический выбор «Продолжить без проверки» для подходящих окон |
| Уведомление о диске | Блокировка соответствующих предупреждений |
| Остальные уведомления | Не соответствующие фильтру уведомления пропускаются |
| Автозапуск | Служба остаётся включённой |
| Реестр | Без изменений |
| Языки | Русский и английский текст предупреждений |

### Установка

Мод отправлен на публикацию в официальный каталог Windhawk: [Pull Request #7943](https://github.com/ramensoftware/windhawk-mods/pull/7943).

Для локальной установки из исходного кода:

1. Установите [Windhawk](https://windhawk.net/).
2. В параметрах включите режим разработчика.
3. На главной странице нажмите «Создать новую модификацию».
4. Замените шаблон полным содержимым файла [disable-usb-scan-fix.wh.cpp](disable-usb-scan-fix.wh.cpp).
5. Скомпилируйте и включите мод, выйдите из режима редактирования.
6. Безопасно переподключите USB-накопитель для проверки.

Для отмены изменений отключите мод в Windhawk.

### Совместимость

Версия 1.1 успешно скомпилирована и протестирована на компьютере автора под Windows 11. Инициализация обоих перехватов и блокировка уведомления подтверждены логами. Окно и уведомление не появились. Другие сборки Windows, языки и отдельный перехват окна полностью не проверены.

> [!WARNING]
> Мод скрывает предупреждения, но не исправляет ошибки файловой системы, не сбрасывает признак Dirty Bit и не предотвращает потерю данных. Создавайте резервные копии важных файлов, безопасно извлекайте накопители и при необходимости проверяйте их вручную.

---

## Version history / История версий

| Version | Changes |
| --- | --- |
| 1.1 | Added selective AutoPlay notification filtering and English/Russian warning matching |
| 1.0 | Initial scan-and-fix dialog interception |

## Author / Автор

**[d-p4d-67](https://github.com/d-p4d-67)** · Developed with ChatGPT assistance / Разработано при помощи ChatGPT.

## License / Лицензия

[MIT License](LICENSE) © 2026 d-p4d-67.

Report issues: [GitHub Issues](https://github.com/d-p4d-67/Disable-USB-Scan-and-Fix-Dialog-Windows-11/issues).
