# Russinovich-glossary
Глоссарий терминов из книги Марка Руссиновича "Внутреннее устройство Microsoft Windows 6е издание"

В попытке прочитать данную книгу я столкнулся с огромным количеством новых для меня аббревиатур, как следствие, я решил найти его на просторах интернета, но к сожалению, не смог. Так что считаю, что его нужно написать самому. Ниже будет представлен список терминов со ссылками на страницу из книги, так как верить кому-то на слово - дурная затея.

- **IRQ** *(Interrupt request / запрос прерывания)*- На аппаратных платформах, поддерживаемых Windows, внешние прерывания ввода-вывода поступают на одну из линий контроллера прерываний. В свою очередь, контроллер прерывает работу процессора по отдельной линии. Как только работа процессора будет прервана, этот процессор требует от контроллера запрос прерывания (Interrupt request, IRQ). **[стр. 107]**
- **IRQL** *(Interrupt request level / уровни запросов прерываний)* -  Хотя контроллеры прерываний устанавливают приоритетность прерываний, Windows устанавливает свою собственную схему приоритетности прерываний, известную как уровни запросов прерываний (IRQL). В ядре IRQL-уровни пред-ставлены в виде номеров от 0 до 31 на системах x86 и в виде номеров от 0 до 15 на системах x64 и IA64, где более высоким номерам соответствуют прерывания с более высоким приоритетом **[стр. 111]**
- **IDT** *(Interrupt dispatch table / таблица диспетчеризации прерываний)* - Контроллер прерываний превращает IRQ в номер прерывания, использует этот номер в качестве индекса в структуре под названием таблица диспетчеризации прерываний (Interrupt dispatch table, IDT) и передает управление соответствующей процедуре обработки прерывания. Во время загрузки системы Windows заполняет IDT указателями на процедуры ядра, обрабатывающими каждое прерывание и исключение **[стр. 107]**
- **Исполняющая система** - Исполняющая система Windows содержит основные службы операционной системы, такие как управление памятью, управление процессами и потоками, безопасность, ввод-вывод, сеть и связь между процессами. **[стр. 57]**
- **Ядро** - Ядро Windows состоит из низкоуровневых функций операционной системы, таких как диспетчеризация потоков, диспетчеризация прерываний и исключений и мультипроцессорная синхронизация. Оно также предоставляет набор подпрограмм и базовых объектов, используемых остальной исполняющей системой для реализации высокоуровневых конструктивных элементов.**[стр. 57]** 
- **Драйвера устройств** - К драйверам устройств относятся как аппаратные драйверы устройств, которые переводят вызовы функций ввода-вывода в запросы ввода-вывода конкретного аппаратного устройства, так и неаппаратные драйверы устройств, такие как драйверы файловой системы и сети. **[стр. 58]**
- **HAL** *(hardware abstraction level / Уровень аппаратных абстракций)*- Уровень аппаратных абстракций (hardware abstraction layer, HAL), являющийся уровнем кода, который изолирует ядро, драйверы устройств и остальную исполняющую систему Windows от аппаратных различий конкретных платформ (таких как различия между материнскими платами).  **[стр. 58]**
- **GUI** *(graphical user interface /графический пользовательский интерфейс)* - Система организации многооконного интерфейса и графики, реализующая функции графического пользовательского интерфейса (graphical user interface, GUI), более известные как имеющиеся в Windows USER- и GDI-функции, предназначенные для работы с окнами, элементами управления пользователь-ского интерфейса и графикой.  **[стр. 58]**
- ACPI (Advanced Configuration and Power interface) - 
- PCI
- USB
- Plug and Play
- x86
- x64
- **ISR** *(Interrupt service routine / процедура обработки прерывания)* - Например, если ситуация была вызвана прерыванием от какого-нибудь устройства, находящийся в ядре обработчик аппаратных системных прерываний передает управление процедуре обработки прерывания (Interrupt service routine, ISR), которую драйвер устройства предоставил для устройства, вызвавшего прерывание. **[стр. 106]**
- Lazy IRQ
- **PIC (Programmable Interrupt Controller / прогруммируемый контроллер прерываний)** - прогруммируемый контроллер прерываний i8259A **[стр. 109]**
- **APIC (Advanced Programmable Interrupt Controller)** - усовершенствованный контроллер прерываний i82489 **[стр. 109]**
- **SAPIC** *(Streamlined Advanced Programmable Interrupt Controller)* - 
- APC
- **UMS** *(user-mode scheduling /планировщик пользовательского режима)* - планировщик пользовательского режима **[стр. 30]**
- **SAS (Secure attention sequence)** - ***безопасная последовательность действий для привлечения внимания. В Windows комбинацию SAS выполняет сочетание Ctrl+Alt+Delete*** [стр. 102]
- Winlogon - обрабатывает интерактивные пользовательские входы в систему и выходы из неё.
- LogonUI
- Userinit - выполняет действия по инициализации пользовательской среды окружения, после чего завершается.
- **SMP (symmetric multiprocessing)** - Windows является симметричной мультипроцессорной операционной системой **[стр. 60]**
- Многозадачность - технология операционной системы для совместного использования одного процессора несколькими потоками выполнения
- **Гиперпотоковость (Hyper-Threading)** - ***Разделение одного физического ядра на 2 логических, для более эффективного управления прерываниями.*** Технология, представленной компанией Intel и предоставляющей два логических процессора для каждого физического ядра. У каждого логического процессора есть свое собственное состояние центрального процессора, но механизм исполнения команд и процессорная кэш-память у них общие. Это позволяет одному логическому центральному процессору успешно работать, в то время как другой логический центральный процессор остановлен (например, после промаха при обращении к кэш-памяти или после неправильно спрогнозированного условного перехода). Алгоритмы диспетчеризации усовершенствованы с учетом оптимального использования машин, допускающих гиперпотоковость, например путем диспетчеризации потоков на простаивающий физический процессор, а не на простаивающий логический процессор на физическом процессоре, где другой логический процессор занят работой. **[стр. 60]**
- **NUMA (non-uniform memory architecture)** - На NUMA-системах процессоры сгруппированы в небольшие блоки, называемые узлами. У каждого узла есть свои собственные процессоры и память, и он подключен к более крупной системе через кэш-когерентную объединяющую шину. Тем не менее Windows на NUMA-системе работает как SMP-система, в ко-торой все процессоры имеют доступ ко всей памяти — при том, что обращение к локальной памяти узла осуществляется быстрее, чем к памяти, подключенной к другим узлам. Система пытается повысить производительность путем диспетчеризации потоков на процессах того же узла, на котором находится используемая **[стр. 60]**
- LSM (lsm.exe) (Диспетчер локальных сеансов) - управляет на  локальной машине состоянием сеансов службы терминалов [стр. 101]
- WDK (Windows Driver Kit) - набор инструментов для разработки драйверов.
- SDK (Software Development Kit) - набор для разработки программного обеспечения.
- **Windows API (Windows application programming interface)** - Интерфейс прикладного программирования Windows API (application programming interface) является интерфейсом системного программирования в пользовательском режиме для семейства операционных систем Windows. До выхода 64-разрядных версий Windows программный интерфейс для 32-разрядных версий операционных систем Windows назывался Win32 API, чтобы его можно было отличить от исходной 16-разрядной версии Windows API (которая служила ин-терфейсом программирования для начальных 16-разрядных версий Windows). В данной книге термин Windows API будет относиться как к 32-, так и к 64-раз-рядным интерфейсам программирования в среде Window **[стр. 19]**
- **API (application programming interface)** - набор готовых классов, процедур, функций, структур и констант, предоставляемых приложением (библиотекой, сервисом) или операционной системой **[Wiki]**
- **Программа** - это статическая последовательность инструкций **[стр. 22]**
- **Процесс** - это контейнер для набора ресурсов, используемых при выполнении экземпляра программы **[стр. 22]**