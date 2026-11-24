ЭТАП 1 — ИСХОДНЫЙ ПАТЧ, НЕ ГОТОВЫЙ МОД MO2.
Три файла изменены на основе присланного FloatingDamageNG-main.zip (4 ноября 2026). Для сборки нужен Windows toolchain и CommonLibVR submodule, отсутствующий в архиве. Готовая DLL ещё не скомпилирована и не проверена в Skyrim.

Правки: собственные цифры HP/урона игрока привязаны к экрану в обоих режимах камеры. Лечение слева, урон справа; урон красный, восстановление зелёное. HP-восстановление, которое уже захвачено NG, суммируется в отдельные секундные интервалы без перезапуска возраста прошлого числа. MP/ST остаются за старым FloatingDamage. Урон по врагам пока не изменён.

Сборка через GitHub: создать собственный fork https://github.com/alandtse/FloatingDamageNG, активировать Actions в форке, заменить три файла в каталоге src из архива, запустить workflow Build (workflow_dispatch), скачать артефакт FloatingDamageNG-binaries. Исходный репозиторий не менять и PR в него не отправлять. Использовать только соответствующую версию исходников. Если версия форка отличается, применить RFAB-stage1.patch и проверить конфликты.

Локальная сборка Windows: установить Visual Studio Build Tools с C++ и xmake; git clone --recurse-submodules https://github.com/alandtse/FloatingDamageNG.git; в корне применить патч командой git apply RFAB-stage1.patch; затем xmake config --mode=releasedbg --yes; xmake build --yes FloatingDamageNG. Сборочный артефакт build/windows/x64/releasedbg/FloatingDamageNG.dll. Скопировать только DLL в отдельную тестовую копию RFAB Tweaks 2.0a/SKSE/Plugins после успешной компиляции.
Исходный код: GPL-3.0-or-later WITH LicenseRef-Modding-Exception, авторы FloatingDamageNG; оригинальные COPYING и EXCEPTIONS.md сохранены в проекте.
