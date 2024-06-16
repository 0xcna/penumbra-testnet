![336988099-b7920ab7-7216-4d76-88b2-7d3715153fc4](https://github.com/0xcna/penumbra-testnet/assets/124911585/bcf7c24a-780d-4c57-9426-cd5cd1ccd238)

<h1 align="center">Penumbra Ceremony Phase 2</h1>


پروژه Penumbra یه شبکه ماژولار و FHE هست که قابلیت معاملات private و ناشناس تو اکوسیستم Cosmos رو برای ما فراهم می‌کنه و به زودی میننتش لانچ میشه

قبلا فاز 1 سرمونی رو شرکت کرده بودیم و اینبار فاز 2 شروع شده که همه می‌تونن شرکت کنن و افزادی که سری قبلی فاز 2 رو زدن هم به خاطر ریستارت شدن این پراگرم باید از اول این مراحل رو طی کنن

سرمونی نیاز به روشن موندن سیستم به مدت 1 تا 3 روز داره

هم با نصب WSL و Ubuntu روی ویندوز می‌تونید بزنید و هم به راحتی با یک سرور VPS با مشخصات خیلی low میتونید انجامش بدید


<h1 align="center">Dependecies</h1>


    sudo apt-get update && sudo apt-get upgrade -y 
    sudo apt-get install curl 
    sudo apt-get install build-essential glibc-source pkg-config libssl-dev clang git-lfs -y


<h1 align="center">Install Penumbra</h1>


    # Install
    curl --proto '=https' --tlsv1.2 -LsSf https://github.com/penumbra-zone/penumbra/releases/download/v0.77.2/pcli-installer.sh | sh

    source $HOME/.cargo/env

    # Check if installed correctly
    pcli --version


 <h1 align="center">Wallet</h1>
 
                                                                                         
برای جنریت ولت یکی از 2 روش زیر رو بسته به اینکه میخواید ولت قبلی ایمپورت کنید یا ولت جدید بسازید انجام بدید

    # Import old wallet
    pcli init soft-kms import-phrase

    # OR

    # Create new wallet (Save seed phrase if you created a new one)
    pcli init soft-kms generate



    # sync wallet
    pcli view sync



    # Check address
    pcli view address 0


از چنل فاست دیسکورد با دادن آدرس توکن تستی بگیرید

    # Check Balance
    pcli view balance


هر درخواست فاست بهتون 100 تا Penumbra میده ولی مکانیزم برنده شدن تو Ceremony اینه که هرچی توکن بیشتری داشته باشید زودتر تو صف جلو میوفتید

می‌تونید با 99 تا از همین 100 تا توکن دستور Ceremony رو اجرا کنید و بعدا فاست بگیرید و دوباره بهش اضافه کنید

در ادامه میگم چطوری به ceremony فعال توکن بیشتری اضافه کنید تا تو صف جلوتر بیوفتید.



<h1 align="center">Ceremony</h1>
                                                                                   


قبل از اجرای Ceremony باید ترمینال رو روی اسکرین بالا بیارید تا بتونید مینیمایز کنید تا در صورت بسته شدن ترمینال، سرمونی قطع نشه

    # Open screen
    screen -S pe

    # start Ceremony
    pcli ceremony contribute --phase 2 --bid 99penumbra


با دستور بالا با 99 تا Penumbra افتادی توی صف سرمونی

با Ctrl + A + D می‌تونید اسکرین رو مینیمایز کنید

با دستور screen -r pe می‌تونید اسکرین رو دوباره بالا بیارید

برای اضافه کردن توکن تستی و جلو افتادن تو صف باید ترمینال رو با Ctrl + C به طور کامل از بین ببرید و دوباره دستور سرمونی رو روی اسکرین جدید شروع کنید به صورت زیر:


    # Open new screen
    screen -S pe2

    # Start Ceremony
    pcli ceremony contribute --phase 2 --bid 99penumbra


<h1>Ctrl + A + D</h1>

اگه ceremony به هر نحوی قطع شد و دوباره خواستید ریستارت کنید کافیه 0 بذارید

    # Optional: Restart Ceremony
    pcli ceremony contribute --phase 2 --bid 0penumbra


افراد به ترتیب مقدار bid که گذاشتن تاییدیه contribute رو میگیرن پس اگه top bid تو داشبورد سرمونی بیشتر بوده ما هم باید بیشتر فاست بگیریم و به bid اضافه کنیم

لینک داشبورد سرمونی


https://summoning.penumbra.zone/

معمولا با 2 3 بار فاست گرفتن و اضافه کردن به سرمونی می‌تونید بیوفتید جلوی صف و سرمونی رو تکمیل کنید

بعد از اتمام Ceremony و رد کردن صف بهتون 2 عبارت Slot و یه هش به عنوان transcript میده مثل عکس زیر


![Screenshot 2024-06-16 171539](https://github.com/0xcna/penumbra-testnet/assets/124911585/8e0eeaa5-27db-40a4-b2eb-f5a11430543b)

مثل عکس زیر توییتش کنید





![Screenshot 2024-06-16 171520](https://github.com/0xcna/penumbra-testnet/assets/124911585/f825c46f-2654-4958-92a0-03ffe39e588a)


فرم زیر رو پر کنید

https://form.asana.com/?k=THhk7qmp3IDwCvXWTPHkow&d=1206052071402903
























