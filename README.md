# MummyMaze Challenge

Öncelikle programı çalıştırıp lisanslamanın nerede yapıldığı, nasıl yapıldığı ve analizini yaparken hangi string’leri aramam gerektiğini düşündüm.

![sc-main](https://raw.githubusercontent.com/echel0nn/ttmomeetupchallenge/master/scs/01.png)



Bu ekranda `Register` butonuna tıklandığında hangi kod bloğunun çalıştığını bulmam gerektiğini ve `Your Name` , `Your Registration Code` ve `Register` string’lerini bulursam eğer bu girdilerin kontrolünün nerede yapıldığına dair ipucu vereceğini düşündüm. 

![sc-main](https://raw.githubusercontent.com/echel0nn/ttmomeetupchallenge/master/scs/02.png)


Bunun dışında kabul etmeyeceğini düşündüğüm name ve registration-code girerek orada alacağım hatanın da, analizi yaparken özellikle bu string’in referansını içeren if-else bloğunun tam tersine gitmeyi düşündüm.

![sc-main](https://raw.githubusercontent.com/echel0nn/ttmomeetupchallenge/master/scs/03.png)


`Register` string’ini arattığımda bulduğum veriler şu şekilde

![sc-main](https://raw.githubusercontent.com/echel0nn/ttmomeetupchallenge/master/scs/04.png)


`Thanks for registering!` string’inin başarılı bir kayıt sonrasında geldiğini düşündüğüm için direkt onun cross referansına baktım.


![sc-main](https://raw.githubusercontent.com/echel0nn/ttmomeetupchallenge/master/scs/05.png)

![sc-main](https://raw.githubusercontent.com/echel0nn/ttmomeetupchallenge/master/scs/06.png)


`Sub_42AAF0`’ı `RegisteringSub` diye yeniden adlandırdım ve bir de başarısız olduğu sub’ı yeniden adlandırırsam çalışma prensibini daha iyi kavrarım, böyle ucundan diye aklıma saçma bi fikir geldi.


![sc-main](https://raw.githubusercontent.com/echel0nn/ttmomeetupchallenge/master/scs/07.png)


![sc-main](https://raw.githubusercontent.com/echel0nn/ttmomeetupchallenge/master/scs/08.png)


Eğer `FailedRegistrationSub` çağrılan her yerde `RegisteringSub`’ı çağırırsam bir şekilde her türlü bu doğrulama ekranını geçerim diye düşündüm. 
Başarısız olanın iki yerde çağrıldığını görüyoruz.

![sc-main](https://raw.githubusercontent.com/echel0nn/ttmomeetupchallenge/master/scs/09.png)



Asla doğruluğunu analiz etmeyeceğim için ikisini de `RegisteringSub` ile değiştirdim.
Tabi böyle öküz gibi deneyince sonuç şey oldu.

![sc-main](https://raw.githubusercontent.com/echel0nn/ttmomeetupchallenge/master/scs/10.png)

![sc-main](https://raw.githubusercontent.com/echel0nn/ttmomeetupchallenge/master/scs/11.png)



Kesinlikle pişman değilim. 
Şimdi de aklıma gelen şey dümdüz bu call’lara giden jump condition’ları tersine çevirmek.

![sc-main](https://raw.githubusercontent.com/echel0nn/ttmomeetupchallenge/master/scs/12.png)

![sc-main](https://raw.githubusercontent.com/echel0nn/ttmomeetupchallenge/master/scs/13.png)



Apply patches canım diyerek, şimdi yeniden deniyorum.

![sc-main](https://raw.githubusercontent.com/echel0nn/ttmomeetupchallenge/master/scs/14.png)

![sc-main](https://raw.githubusercontent.com/echel0nn/ttmomeetupchallenge/master/scs/15.png)


Oley!
