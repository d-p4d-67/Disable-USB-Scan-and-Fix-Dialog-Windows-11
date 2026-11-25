<div align="center">

# Disable USB Scan and Fix Dialog Windows 11

**Keep AutoPlay. Skip unwanted disk repair prompts.**

![Windows 11](https://img.shields.io/badge/Windows-11-0078D4?logo=windows&logoColor=white)
![Windhawk](https://img.shields.io/badge/Windhawk-Mod-5856D6)
![Version](https://img.shields.io/badge/version-1.2-blue)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?logo=cplusplus&logoColor=white)
[![MIT License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

[English](#english) · [Русский](#русский) · [Source code](disable-usb-scan-fix.wh.cpp) · [Windhawk submission #7943](https://github.com/ramensoftware/windhawk-mods/pull/7943)

</div>

---

## English

A lightweight [Windhawk](https://windhawk.net/) mod for Windows 11 that suppresses the USB drive scan-and-repair dialog and its associated AutoPlay notification without disabling the AutoPlay service.

![USB Scan and Fix dialog blocked](https://raw.githubusercontent.com/d-p4d-67/Disable-USB-Scan-and-Fix-Dialog-Windows-11/main/Disk_Check_dialog.png)

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
- Tested on Windows 11 with a Russian display language. Both hooks initialized successfully, and USB disk warning notification blocking was confirmed in debug logs. English text matching, other Windows builds, and independent dialog interception have not been verified.
- Uses `TaskDialogIndirect` and `IToastNotifier::Show` hooks in Explorer (x86-64). Warning text is matched in English or Russian. Unrecognized content is passed through.

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

Протестировано на Windows 11 с русским языком интерфейса. Инициализация обоих перехватов и блокировка уведомления о проверке USB-накопителя подтверждены логами. Английский интерфейс, другие сборки Windows и отдельный перехват диалогового окна не проверены.

> [!WARNING]
> Мод скрывает предупреждения, но не исправляет ошибки файловой системы, не сбрасывает признак Dirty Bit и не предотвращает потерю данных. Создавайте резервные копии важных файлов, безопасно извлекайте накопители и при необходимости проверяйте их вручную.

---

## Version history / История версий

| Version | Changes |
| --- | --- |
| 1.2 | Retained hook implementation DLLs, restricted injection to Explorer and x86-64, improved DLL loading and typed hooks, added project homepage |
| 1.1 | Added selective AutoPlay notification filtering and English/Russian warning matching |
| 1.0 | Initial scan-and-fix dialog interception |

## Author / Автор

**[d-p4d-67](https://github.com/d-p4d-67)** · Developed with ChatGPT assistance / Разработано при помощи ChatGPT.

## License / Лицензия

[MIT License](LICENSE) © 2026 d-p4d-67.

Report issues: [GitHub Issues](https://github.com/d-p4d-67/Disable-USB-Scan-and-Fix-Dialog-Windows-11/issues).
