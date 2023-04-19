# SSMS
Sports Shop Management System
Code for Log-In Button 
if (textBox1.Text == "") { MessageBox.Show("Enter Username !!", "Name"); } 
else if (textBox2.Text == "") { MessageBox.Show("Enter Password !!", "College"); } 
else if (textBox1.Text == "Sports Shop" && textBox2.Text == "pcce")
 { this.Hide(); 
Form frm6 = new Form6(); 
frm6.ShowDialog(); } 
else 
{ MessageBox.Show("Invalid Credential", "Sports Shop"); }
Code for Insert Button try { string MyConnection2 "datasource=localhost;Initial Catalog=dbms;port=3306;username=root;password=123"; string Query = "insert into product(p_code,price,p_name,category,quantity) values('" + this.Code.Text + "','" this.Price.Text + "','" this.Pname.Text + "','" this.Category.Text + "','" this.Quantity.Text + "');"; MySqlConnection MyConn2 new MySqlConnection(MyConnection2); MySqlCommand MyCommand2 new MySqlCommand(Query, MyConn2); MySqlDataReader MyReader2; MyConn2.Open(); MyReader2 MyCommand2.ExecuteReader(); MessageBox.Show("Data has been saved."); while (MyReader2.Read()) { } MyConn2.Close(); } catch (Exception ex) { MessageBox.Show(ex.Message); }
