# Zodiac

1. Baris kode ini membuat objek Scanner baru yang disebut input. Objek ini akan digunakan untuk membaca input dari pengguna melalui System.in. Baris ini mendeklarasikan variabel repeat dengan tipe data boolean yang diinisialisasi dengan true. Variabel ini akan digunakan untuk mengontrol perulangan atau iterasi dalam program. Ketika bernilai true, itu menunjukkan bahwa program akan dijalankan atau diulang.

       Scanner input = new Scanner(System.in);
            boolean repeat = true;

2. Potongan kode tersebut memungkinkan pengguna untuk memasukkan tanggal dan bulan secara berulang, menampilkan tanda zodiak yang sesuai, dan keluar dari program jika memasukkan "0 0". Namun, untuk menjalankan program ini, perlu ada definisi dari fungsi determineZodiacSign() yang menentukan tanda zodiak berdasarkan tanggal dan bulan yang diberikan.

       while (repeat) {
                  int tanggal, bulan;
                  System.out.println("\nMasukkan tanggal lahir atau masukkan 0 0 untuk keluar");
                  System.out.print("Tanggal: ");
                  tanggal = input.nextInt();
                  System.out.print("Bulan: ");
                  bulan = input.nextInt();
      
                  if (tanggal == 0 && bulan == 0) {
                      System.out.println("Terima kasih :)");
                      repeat = false;
                  } else {
                      String zodiacSign = determineZodiacSign(tanggal, bulan);
                      if (zodiacSign.equals("Invalid")) {
                          System.out.println("Tanggal yang dimasukkan tidak masuk akal");
                      } else {
                          System.out.println("Tanggal tersebut mempunyai Zodiac " + zodiacSign);
                      }
                  }
              }
              input.close();

3. Code tersebut adalah sebuah fungsi dalam bahasa pemrograman Java yang menerima dua parameter integer, tanggal dan bulan. Fungsi ini menentukan zodiak berdasarkan kombinasi tanggal dan bulan yang diberikan. Melalui serangkaian pernyataan if-else if, fungsi tersebut memeriksa rentang tanggal untuk setiap zodiak dan mengembalikan zodiak yang sesuai dengan parameter yang diberikan.  jika tidak ada zodiak yang sesuai dengan kombinasi tanggal dan bulan yang diberikan, maka fungsi akan mengembalikan string "Invalid".

       public static String determineZodiacSign(int tanggal, int bulan) {
            if ((bulan == 3 && tanggal >= 21) || (bulan == 4 && tanggal <= 19)) {
                return "Aries";
            } else if ((bulan == 4 && tanggal >= 20) || (bulan == 5 && tanggal <= 20)) {
                return "Taurus";
            } else if ((bulan == 5 && tanggal >= 21) || (bulan == 6 && tanggal <= 20)) {
                return "Gemini";
            } else if ((bulan == 6 && tanggal >= 21) || (bulan == 7 && tanggal <= 22)) {
                return "Cancer";
            } else if ((bulan == 7 && tanggal >= 23) || (bulan == 8 && tanggal <= 22)) {
                return "Leo";
            } else if ((bulan == 8 && tanggal >= 23) || (bulan == 9 && tanggal <= 22)) {
                return "Virgo";
            } else if ((bulan == 9 && tanggal >= 23) || (bulan == 10 && tanggal <= 22)) {
                return "Libra";
            } else if ((bulan == 10 && tanggal >= 23) || (bulan == 11 && tanggal <= 21)) {
                return "Scorpio";
            } else if ((bulan == 11 && tanggal >= 22) || (bulan == 12 && tanggal <= 21)) {
                return "Sagittarius";
            } else if ((bulan == 12 && tanggal >= 22) || (bulan == 1 && tanggal <= 19)) {
                return "Capricorn";
            } else if ((bulan == 1 && tanggal >= 20) || (bulan == 2 && tanggal <= 18)) {
                return "Aquarius";
            } else if ((bulan == 2 && tanggal >= 19) || (bulan == 3 && tanggal <= 20)) {
                return "Pisces";
            } else {
                return "Invalid";
            }
        }
