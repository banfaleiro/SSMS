//# SSMS (Sports Shop Management System)
//Generic Code for Log-In Button 
if (textBox1.Text == "") { MessageBox.Show("Enter Username !!", "Name"); } 
else if (textBox2.Text == "") { MessageBox.Show("Enter Password !!", "College"); } 
else if (textBox1.Text == "Sports Shop" && textBox2.Text == "pcce")
 { this.Hide(); 
Form frm6 = new Form6(); 
frm6.ShowDialog(); } 
else 
{ MessageBox.Show("Invalid Credential", "Sports Shop"); }
//Generic Code for Insert Button 
try 
{ string MyConnection2 "datasource=localhost;Initial Catalog=dbms;port=3306;username=root;password=123"; 
string Query = "insert into product(p_code,price,p_name,category,quantity) values('" + this.Code.Text + "','" this.Price.Text + "','" this.Pname.Text + "','" this.Category.Text + "','" this.Quantity.Text + "');"; //Connection String
MySqlConnection MyConn2 new MySqlConnection(MyConnection2); 
MySqlCommand MyCommand2 new MySqlCommand(Query, MyConn2); 
MySqlDataReader MyReader2; MyConn2.Open(); 
MyReader2 MyCommand2.ExecuteReader(); MessageBox.Show("Data has been saved."); 
while (MyReader2.Read()) { } 
MyConn2.Close(); } 
catch (Exception ex) 
{ MessageBox.Show(ex.Message); }
//Generic Code for Update Button
try
{string MyConnection2 = "datasource=localhost;Initial Catalog=dbms;port=3306;username=root;password=123";
string Query = "update product set p_code='" + this.Code.Text + "',price='" + this.Price.Text + "',p_name='" + this.Pname.Text + "',category='" + this.Category.Text + "',quantity='" + this.Quantity.Text + "'where p_code='" + this.Code.Text + "';";
 MySqlConnection MyConn2 = new MySqlConnection(MyConnection2);
 MySqlCommand MyCommand2 = new MySqlCommand(Query, MyConn2);
 MySqlDataReader MyReader2;
 MyConn2.Open();
 MyReader2 = MyCommand2.ExecuteReader(); MessageBox.Show("Data has been updated");
 while (MyReader2.Read()){ }
 MyConn2.Close(); }
catch (Exception ex)
{ MessageBox.Show(ex.Message);}}
//Generic Code for Search Button
try
{
string MyConnection2 = "datasource=localhost;Initial Catalog=dbms;port=3306;username=root;password=123";
string Query = "select * from product where p_code='" + this.Code.Text + "'";
MySqlConnection MyConn2 = new MySqlConnection(MyConnection2);
MySqlCommand MyCommand2 = new MySqlCommand(Query, MyConn2);
MySqlDataAdapter MyAdapter = new MySqlDataAdapter();
MyAdapter.SelectCommand = MyCommand2;
DataTable dTable = new DataTable();
MyAdapter.Fill(dTable);
dataGridView1.DataSource = dTable; 
}
catch (Exception ex)
{
MessageBox.Show(ex.Message);
}
//Generic Code for Delete Button
try
{
string MyConnection2 = "datasource=localhost; Initial Catalog=dbms;port=3306;username=root;password=123";
string Query = "delete from product where p_code='" + this.Code.Text + "';";
MySqlConnection MyConn2 = new MySqlConnection(MyConnection2);
MySqlCommand MyCommand2 = new MySqlCommand(Query, MyConn2);
MySqlDataReader MyReader2;
MyConn2.Open();
MyReader2 = MyCommand2.ExecuteReader();
MessageBox.Show("Data has been Deleted");
while (MyReader2.Read())
{}
MyConn2.Close();}
catch (Exception ex)
{MessageBox.Show(ex.Message);}
Code for Reset
Code.Clear(); //Code is textbox name
dataGridView1.DataSource = null;
Code for Next
this.Hide();
Form frm7 = new Form7();//frm7 is the name of the C# form
frm7.ShowDialog();


