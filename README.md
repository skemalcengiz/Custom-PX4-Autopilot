01 Ağustos 2021

Said Kemal Cengiz

Bu çalışmada halihazırda var olan "sensor_combined" topicine kendi oluşturmuş olduğumuz "my_module" modülü üzerinden subscribe olunarak ivmeölçer değerleri anlık olarak okunmuş ve yine kendi oluşturmuş olduğumuz 
	
	my_topic
	
isimli topice publish edilmiştir.			
										
										
  Oluşturmuş olduğumuz modül, PX4 içerisinde var olan modüllerdeki yöntem 	
     kullanılarak hazırlanmıştır. Buna göre, Nesne Yönelimli Programlama    
 mantığı kullanılarak class yapısında kodlar hazırlanmış olup NuttX işletim	
	sistemi üzerinde işlem sırasına göre modül önceliklendirilmiştir.	
										
										
			    /src/modules/my_module/				
	     dizini altından oluşturulan modülün kaynak kodlarına,		
	   dosyalama sistemine ve kod formatına göz gezdirilebilir. 		
				Bununla beraber,				
				     /msg/					
	dizini altından da "my_topic" isimli topicin içeriğine bakılabilir.	
										
										
				Oluşturulan modül,				
			boards/omnibus/f4sd/default.cmake			
			     dosyası içerisindeki				
				     MODULES					
		başlığı altına derlenebilmesi açısından eklenmiştir.		
										
										
 			ROMFS/px4fmu_common/init.d/rcS			
				dosyası içerisine				
				 my_module start				
		komutu eklenerek modülün başlangıçtan itibaren, 		
   herhangi bir yerden çağırılmaya ihtiyaç duymadan çalışmaya başlaması	
   		           sağlanmıştır. Ek olarak, 				
			  src/modules/logger/params.c				
			     dosyası içerisindeki 				
				SDLOG_MODE 2 					
 olarak ayarlanmıştır ki başlangıçtan itibaren SD Karta veri kaydı başlasın.
