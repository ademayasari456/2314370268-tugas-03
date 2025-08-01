// Use DBML to define your database structure
// Docs: https://dbml.dbdiagram.io/docs

Table pengarang {
  id_pengarang integer [primary key]
  nama_p varchar
  id_penerbit integer
}

Table penerbit {
  id_penerbit integer [primary key]
  nama_pt varchar
}

table buku{
  id_buku integer [primary key]
  judul_buku varchar 
  id_pengarang integer [primary key]
  id_penerbit integer [primary key]
  jumlah_hal integer 
}

table supplier{
  id_supplier integer [primary key]
  nama_customer varchar
  alamat_customer varchar
  kota_customer varchar 
  nomor_custoner varchar 
}

table orders{
  no_po varchar
  tgl_po varchar
  id_supplier integer [primary key]
}

table detil{
  no_po varchar
  id_buku integer [primary key]
  qty_beli varchar
  harga_sat varchar
}

Ref: pengarang.id_pengarang > buku.id_pengarang
Ref: penerbit.id_penerbit > buku.id_penerbit
Ref: supplier.id_supplier > orders.id_supplier
Ref: orders.no_po > detil.no_po
Ref: detil.id_buku > buku.id_buku
