Kullanıcı girdisi ve film girdisi alan ve bunları dizilerde saklayıp
daha sonrasında kullanıcıya gösterebilen bir program yazdım.

öncelikle dizilerimi oluşturdum, daha sonra switch case ile
kullanıcı arayüzünü yaptım burada her bir sayıya denk düşen
case kullanıcının yapmak istediği işlemin fonksiyonunu çağırıyor.

scanner.close(); kullanıcıdan veri almayı kesmek için kullanılıyor 
her bir fonksiyonun sonunda tek tek kullanmaktansa switch case döngüsünün
sonunda tek bir sefer kullanmayı daha mantıklı buldum 

daha sonra kullanıcıdan film ve müşteri verilerini scanner ile alıp

yine aynı sistemle daha önceden girilmiş olan müşteri ve film bilgileriyle
kullanıcıya bilet oluşturmasını sağlıyor.

scanner.nextline(); kullanıcının girdiği verinin tamamını almak için 
kullandım. Kullanıcının adı ve soyadı boşluklarla yazılmış olsa da
bu boşluklar dahil olmak üzere verinin tamamını bir string olarak alacak.

en sonunda ise biletleri dizelerin içeriğini for döngüsüyle okuyarak 
her bir bileti oluşturulma sırasına göre sıralıyor.