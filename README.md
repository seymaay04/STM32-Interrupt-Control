# STM32 Interrupt ve Flash Kontrolü

Bu proje, STM32F103C8T6 (Blue Pill) mikrodenetleyicisi üzerinde C dili ve HAL kütüphanesi kullanılarak geliştirilmiş, donanım kesmeleri ve kalıcı bellek yönetimini içeren kapsamlı bir gömülü sistem uygulamasıdır.

## Proje İçeriği ve Kazanımlar

*   **Zamanlayıcı Kesmeleri:** TIM2 modülü saniyede 1 kere kesme oluşturacak şekilde ayarlanmış ve LED'in yanıp sönmesi HAL_Delay kullanılmadan sağlanmıştır.
*   **Harici Kesmeler:** Buton okumaları GPIO harici kesmeleri (EXTI) ile tetiklenerek sistemin anında tepki vermesi sağlanmıştır.
*   **Flash Bellek Yönetimi:** Kullanıcının ayarladığı yanıp sönme sayıları (blink_count), güç kesilmesine karşı doğrudan mikrodenetleyicinin dahili Flash belleğine yazılarak kalıcı hale getirilmiştir. 
*   **İlk Açılışta Sıfırlama:** Sisteme güç verildiği (başlangıç) anında butonun en az 3 saniye basılı tutulması durumunda blink_count değerini fabrika ayarı olan 4'e döndüren bir sıfırlama mekanizması eklenmiştir.

## Kullanılan Teknolojiler
*   **Programlama Dili:** C
*   **Donanım:** STM32F103C8T6
*   **Temel Modüller:** GPIO, TIM2 (Timer), NVIC (Interrupt Controller), Flash Memory Controller
