# Pacmann-OOP-Project-akhir
Project akhir untuk kelas Python 1 dan 2


1. Background
   membuat sistem sistem kasir dengan self service untuk kebutuhan suatu supermarket, sehingga customer dapat memasukkan item yang dibeli serta dapat mengubah item yang dibeli

2. Tool
  Python

3. Objective
   Membuat sistem kasir yang memudahkan customer untuk berbelanja
   Membuat fitur seperti menambah, mengurangi, reset dan akumulasi item yang dibeli

4. Program Description
   1. Membuat class Transaction
      class Transaction:
      def __init__(self, nama_item, jumlah_item, harga_per_item):
        self.nama_item = nama_item
        self.jumlah_item = jumlah_item
        self.harga_per_item = harga_per_item
        self.total_transaction = self.jumlah_item * self.harga_per_item
      
   2. Method
      def add_item(self, nama_item, jumlah_item, harga_per_item):
        self.nama_item = nama_item
        self.jumlah_item = jumlah_item
        self.harga_per_item = harga_per_item
        self.total_transaction = self.jumlah_item * self.harga_per_item

    def delete_item(self):
        self.nama_item = ""
        self.jumlah_item = 0
        self.harga_per_item = 0
        self.total_transaction = 0

    def reset_transaction(self):
        self.nama_item = ""
        self.jumlah_item = 0
        self.harga_per_item = 0
        self.total_transaction = 0

    def check_order(self):
        if self.total_transaction > 500000:
            discount = self.total_transaction * 10 / 100
            grand_total = self.total_transaction - discount
        elif self.total_transaction > 300000:
            discount = self.total_transaction * 8 / 100
            grand_total = self.total_transaction - discount
        elif self.total_transaction > 200000:
            discount = self.total_transaction * 5 / 100
            grand_total = self.total_transaction - discount
        else:
            discount = 0
            grand_total = self.total_transaction
        return discount, grand_total
        
        
   3. Mencoba memasukkan data
      trnsct_123 = Transaction("Mobil", 2, 1000000)
      trnsct_124 = Transaction("Mie", 1, 5000)
      trnsct_125 = Transaction("Tempe", 3, 3000)
      
   4. Membuat akumulasi dan diskon
      transactions = [trnsct_123, trnsct_124, trnsct_125]

      grand_total = 0

      for trnsct in transactions:
          grand_total += trnsct.total_transaction
    
      discount = 0
      if grand_total > 200000:
        discount = grand_total * 0.05
      elif grand_total > 300000:
        discount = grand_total * 0.08
      elif grand_total > 500000:
        discount = grand_total * 0.1
    
      grand_total -= discount
      
  5. Membuat tabel
     print("="*50)
     print("{:<20} {:<10} {:<10} {:<15}".format("Nama Item", "Jumlah", "Harga", "Total"))
     print("="*50)
    for trnsct in transactions:
      print("{:<20} {:<10} {:<10} {:<15}".format(trnsct.nama_item, trnsct.jumlah_item, trnsct.harga_per_item, trnsct.total_transaction))
    print("="*50)
    print("{:<20} {:<10} {:<10} {:<15}".format("", "", "Grand Total", grand_total))
    print("{:<20} {:<10} {:<10} {:<15}".format("", "", "Discount", discount))
    print("="*50)
 
 6. Hasil
    ![Opera Snapshot_2023-02-05_205123_localhost](https://user-images.githubusercontent.com/88522243/216823376-c45bcbf0-e623-4365-b6c2-32a268af3246.png)
