# coursera-sql-my-final-assignment

Bu proje Coursera.org'dan satın aldığım, Databases and SQL for Data Science with Python eğitiminin bitirme ödevi olarak verilmişti. Ben de bu ödevi nasıl başarı ile tamamladığımı sizinle paylaşacağım.

Ödevin amacı: Üç farklı veriseti üzerinden istenilen kayıtların başarılı bir şekilde sorgulanması. Verisetleri Chicago, ABD'de yaşayan insanların ve o insanların işlediği suçlar, eğitim seviyeleri vs çeşitli bilgiler içeriyor.

Verisetlerimizin kaynağı bizimle önceden paylaşılmıştı. 
  - [Census Data](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork22-2022-01-01)
  - [Chicago Public Schools](https://data.cityofchicago.org/Education/Chicago-Public-Schools-Progress-Report-Cards-2011-/9xs2-f89t?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork22-2022-01-01)
  - [Chicago Crime Data](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork22-2022-01-01)

Bu linklerden verisetlerimizi indiriyoruz. Pandas kütüphanesi ile verisetlerimizi okuyoruz. .csv dosyaları ile .ipynb dosyanızın aynı dizinde olduğundan emin olun, eğer değilse .csv dosyalarınızın dizin yolunu doğru bir şekilde belirtmelisiniz.

![image](https://user-images.githubusercontent.com/28548881/210233262-add99d55-1360-437e-8047-d55e6e2d89bf.png)

Ardından SQL sorguları kullanacağımız için bir veritabanına ihtiyacımız var. SQLite3 veritabanını kullanacağız. Projemize import edip bağlantı oluşturuyoruz. Bağlantımızı kurduktan sonra okuduğumuz verisetlerini .to_sql fonksiyonu ile veritabanımıza gönderiyoruz.

![image](https://user-images.githubusercontent.com/28548881/210235547-59e587a5-bc0c-4c99-861c-8ef154c89eab.png)

Kaydettiğimiz dosyayı bir VTYS'nde açmamıza gerek kalmadan Jupyter Notebook ile çalıştırabiliyoruz ve üstünde sorgular gerçekleştirebiliyoruz. Sorgu işlemlerimizi yapabilmemiz için bir kütüphane yüklememiz gerekiyor.

  - [IPython-SQL](https://github.com/catherinedevlin/ipython-sql)

Jupyter Notebook'te magic commands olarak geçen bazı komutlar var. Python Kernel kullanırken sanki bir VTYS'ndeymiş gibi SQL sorguları yazarak veritabanımız üzerinde çalışabileceğiz. Aşağıdaki terminal komutu ile kütüphanemizi yüklememiz gerekiyor. Dilerseniz komutun başına ! koyarak Jupyter Notebook hücresi içinde de çalıştırabilirsiniz.

```
pip install ipython-sql
```
```
!pip install ipython-sql
```

![image](https://user-images.githubusercontent.com/28548881/210246162-47938b7f-fea9-46d6-a3bf-1ac28f2d4dfb.png)

Kütüphanemizi yükledik. Şimdi de import işlemini yapacağız fakat biraz farklı olacak. Python kütüphanesi gibi import {kütüphane-adı} şeklinde değil. Zaten yukarıda bıraktığım linkte nasıl kullanıldığını güzel bir şekilde örnekleriyle açıklamış durumda. Ben sadece kullandığım kadarını açıklamak istiyorum.

Jupyter Notebook magic commandleri % karakteri ile kullanılıyor. Eğer tek satırlık bir komut kullanacaksanız %, birden fazla satırlık bir komut ise %% olarak başlamalısınız.

```
%load_ext sql
```
```
%sql sqlite:///database.db
```
![image](https://user-images.githubusercontent.com/28548881/210246716-44755dba-13da-4887-8761-f339573ceba3.png)

Eğer bu noktaya kadar bir hata almadıysanız işlemleriniz doğrudur ve bir problem yoktur. 

#### Şimdi SQL sorguları yazarak istediğimiz verilere ulaşabiliriz.

![image](https://user-images.githubusercontent.com/28548881/210246955-5db0a795-a870-49da-8194-4431f7993b93.png)

![image](https://user-images.githubusercontent.com/28548881/210247028-3c7da13b-fc21-4725-826f-5431d2d913d1.png)

