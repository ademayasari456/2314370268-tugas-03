// Use DBML to define your database structure
// Docs: https://dbml.dbdiagram.io/docs

Table pencipta {
  id_pencipta integer [primary key]
  merk_p varchar
  id_sales integer
}

Table sales {
  id_sales integer [primary key]
  merk_pt varchar
}

table tas{
  id_tas integer [primary key]
  kode_tas varchar 
  id_pencipta integer [primary key]
  id_sales integer [primary key]
  jumlah_barang integer 
}

table supplier{
  id_supplier integer [primary key]
  nama_customer varchar
  alamat_customer varchar
  kota_customer varchar 
  nomor_customer varchar 
}

table orders{
  no_po varchar
  tgl_po varchar
  id_supplier integer [primary key]
}

table detil{
  no_po varchar
  id_tas integer [primary key]
  qty_beli varchar
  harga_sat varchar
}

Ref: pencipta.id_pencipta > tas.id_pencipta
Ref: sales.id_sales > tas.id_sales
Ref: supplier.id_supplier > orders.id_supplier
Ref: orders.no_po > detil.no_po
Ref: detil.id_tas > tas.id_tas
