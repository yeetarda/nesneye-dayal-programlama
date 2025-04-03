# nesneye-dayalı-programlama
Piri Reis Üniversitesi 2025-2026 Bİlgisayar Programcılığı 1. sınıf 2. dönem nesneye dayalı programlama dersi film önerme makinesi

    import java.util.Scanner;

    public class sinemamusterikayitsistemi {
    
    
    
    static int maxf = 10;
    static int maxm = 20;



    static String[] filmadi = new String[maxf];
    static int[] filmsure = new int[maxf];
    static String[] filmtur = new String[maxf];



    static String[] musteriad = new String[maxm];
    static String[] musteriemail = new String[maxm];



    static String[][] biletler = new String[maxm][maxf];



    static int filmler = 0;
    static int musteriler = 0;

    public static void main() {
        Scanner scanner = new Scanner(System.in);
        int secim;

        do {
            System.out.println("\nLutfen yapmak istediginiz islemi girin");
            System.out.println("1-Film Ekle");
            System.out.println("2-Musteri Ekle");
            System.out.println("3-Bilet Kaydi");
            System.out.println("4-Biletleri Listele");
            System.out.println("5-cikis");
            System.out.print("Hangi islemi yapmak istersiniz");
            secim = scanner.nextInt();
            scanner.nextLine();

            switch (secim) {
                case 1:
                    filmekle(scanner);
                    break;
                case 2:
                    musteriekle(scanner);
                    break;
                case 3:
                    biletkayit(scanner);
                    break;
                case 4:
                    biletlistele();
                    break;
                case 5:
                    System.out.println("iyi gunler dileriz");
                    break;
            }
        } while (secim != 5);

        scanner.close();
    }
    static void filmekle(Scanner scanner) {
        if (filmler < maxf) {
            System.out.print("\nFilm adi: ");
            filmadi[filmler] = scanner.nextLine();
            System.out.print("Film suresi (dakika): ");
            filmsure[filmler] = scanner.nextInt();
            scanner.nextLine();
            System.out.print("Film turu: ");
            filmtur[filmler] = scanner.nextLine();

            filmler++;
            System.out.println("\nFilm basariyla eklendi");
        } else {
            System.out.println("\ndaha fazla film ekleyemezsiniz");
        }
    }


    static void musteriekle(Scanner scanner) {
        if (musteriler < maxm) {
            System.out.print("\nMusteri adi: ");
            musteriad[musteriler] = scanner.nextLine();
            
            System.out.print("Musteri email adresi: ");
            musteriemail[musteriler] = scanner.nextLine();
            musteriler++;
            
            System.out.println("\nMusteri basariyla eklendi");
            
        } else {
            System.out.println("\nDaha fazla musteri ekleyemezsiniz");
        }
    }



    static void biletkayit(Scanner scanner) {
        if (musteriler == 0 || filmler == 0) {
            System.out.println("\nMusteri ve film ekleyiniz");
            return;
        }

        System.out.println("\nMevcut musteriler\n:");
        for (int i = 0; i < musteriler; i++) {
            System.out.println(i + 1 + ". " + musteriad[i] + " - " + musteriemail[i]);
        }

        System.out.print("\nBir musteri seciniz\n (1-" + musteriler + "): ");
        int musterisecimi = scanner.nextInt() - 1;
        scanner.nextLine();

        if (musterisecimi < 0 || musterisecimi >= musteriler) {
            System.out.println("\nLutfen duzgun secim yapiniz");
            return;
        }

        System.out.println("\nMevcut filmler:\n");
        for (int i = 0; i < filmler; i++) {
            System.out.println(i + 1 + ". " + filmadi[i] + " - " + filmsure[i] + " dakika - Tur: " + filmtur[i]);
        }

        System.out.print("\nBir film secin (1-" + filmler + "): ");
        int filmsecimi = scanner.nextInt() - 1;
        scanner.nextLine();

        if (filmsecimi < 0 || filmsecimi >= filmler) {
            System.out.println("\nLutfen duzgun secim yapiniz");
            return;
        }

        biletler[musterisecimi][filmsecimi] = filmadi[filmsecimi];
        System.out.println("\nbiletiniz onaylanmistir");
    }


    static void biletlistele() {
        for (int i = 0; i < musteriler; i++) {
            System.out.println("\nMusteri: " + musteriad[i]);
            System.out.println("Email: " + musteriemail[i]);
            System.out.println("İzledigi filmler:");
    
            int sayac = 0;
    
            for (int j = 0; j < filmler; j++) {
                if (biletler[i][j] != null) {
                    System.out.println("- " + biletler[i][j]);
                    sayac++;
            }
    
            if (sayac == 0) {
                System.out.println("Hic film yok");
            }
        }
    }
    }

