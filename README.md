# PROMOS
Aditya Yulis Kusdiyanto (19.11.2795)
S1 Informatika 04
Promos adalah program yang berfungsi untuk menambahkan item ke sebuah keranjang digital

## Scope of Functions
- Menambahkan barang dengan teknik MVC 
- Penambahan fungsi Voucer
- Penambahan message box saat menghapus item
- Melihat makanan/minumam apa saja yang ditambahkan

### How does it works ? 
- fungsi MainWindowController.cs digunakan untuk melakukan beberapa operasi. Seperti menambahkan item dan voucher, menghapus item dan voucher, lalu untuk mendapatkan data list dari item yang dibeli dan voucher yang digunakan.
- model yang digunakan yaitu model item untuk makanan atau minuman, model keranjangBelanja untuk menaruh pembelian, model payment untuk mengurusi total harga beli, dan model Voucher untuk daftar vouchernya
 
#### Alur Program :
- Menu yang ditawarkan : 

 ```c#
  private void generateContentMenu()
        {
            Item Menu1 = new Item("Coffe Late", 30000);
            Item Menu2 = new Item("Black Tea", 20000);
            Item Menu3 = new Item("Pizza", 75000);
            Item Menu4 = new Item("Milk Shake", 15000);
            Item Menu5 = new Item("Fried Frice Special", 45000);
            Item Menu6 = new Item("Watermelon Juice", 25000);
            Item Menu7 = new Item("Lemon Squash", 30000);

            menuController.addItem(Menu1);
            menuController.addItem(Menu2);
            menuController.addItem(Menu3);
            menuController.addItem(Menu4);
            menuController.addItem(Menu5);
            menuController.addItem(Menu6);
            menuController.addItem(Menu7);

            listMenu.Items.Refresh();

        }
        
  ```
        
- Voucher :
 ```c#
 
 private void generateContentPromo()
        {
            Diskon diskon1 = new Diskon("Promo Awal tahun Diskon 25 % ", 25000);
            Diskon diskon2 = new Diskon("Promo Tebus Murah Diskon 30 % atau maksimal 30.000", 30000);
            Diskon diskon3 = new Diskon("Promo Natal Potongan 10000", 10000);

            promoController.addPromo(diskon1);
            promoController.addPromo(diskon2);
            promoController.addPromo(diskon3);

            listBoxDaftarPromo.Items.Refresh();
        }
        
  
 ```
 
 - Keranjang pesanan yang menampilkan belanjaan dan voucher :
  ```c#
  
  namespace WARUNG.Model
{
    class KeranjangBelanja
    {
        List<Item> itemkeranjangBelanja;
        public List<Diskon> diskonDipakai;
        Bayar payment;
        onKeranjangBelanjaChangedListener onKeranjangBelanjaChangedListener;

        public KeranjangBelanja(Bayar payment, onKeranjangBelanjaChangedListener onKeranjangBelanjaChangedListener)
        {
            this.payment = payment;
            this.onKeranjangBelanjaChangedListener = onKeranjangBelanjaChangedListener;
            this.itemkeranjangBelanja = new List<Item>();
            this.diskonDipakai = new List<Diskon>();
        }
        public List<Item> getItems()
        {
            return this.itemkeranjangBelanja;
        }

        public List<Diskon> getDiskon()
        {
            return this.diskonDipakai;
        }
        
 ```    
        

### Tools
- Visual Studio 2019
- C# Langugage
