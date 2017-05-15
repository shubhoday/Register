# Register
This is the repository for registration
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="Register.aspx.cs" Inherits="Register" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
    <style type="text/css">
        .auto-style1 {
            width: 80%;
        }
        .auto-style2 {
            width: 206px;
        }
        .auto-style3 {
            width: 760px;
        }
        .auto-style4 {
            width: 206px;
            height: 42px;
        }
        .auto-style5 {
            width: 760px;
            height: 42px;
        }
        .auto-style6 {
            width: 206px;
            height: 36px;
        }
        .auto-style7 {
            width: 760px;
            height: 36px;
        }
        .auto-style8 {
            width: 210px;
            height: 24px;
        }
        .auto-style9 {
            width: 766px;
            height: 27px;
        }
    </style>
</head>
<body>
    <form id="form1" runat="server">
    <div>
    
        <table class="auto-style1">
            <tr>
                <td class="auto-style8">Product Name:</td>
                <td class="auto-style9">
                    <asp:TextBox ID="TextBox1" runat="server" Width="170px" required></asp:TextBox>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                </td>
            </tr>
            <tr>
                <td class="auto-style2">Product&nbsp; Category:</td>
                <td class="auto-style3">
                    <asp:DropDownList ID="DropDownList1" runat="server" Height="19px" Width="145px">
                        <asp:ListItem>Mobile and accessories</asp:ListItem>
                        <asp:ListItem>Powder Detergent</asp:ListItem>
                    </asp:DropDownList>
                    <br />
                </td>
            </tr>
            <tr>
                <td class="auto-style2">Quantity:</td>
                <td class="auto-style3">
                    <asp:TextBox ID="TextBox2" runat="server" Width="170px" required></asp:TextBox>
                    <br />
                </td>
            </tr>
            <tr>
                <td class="auto-style2">Price:</td>
                <td class="auto-style3">
                    <asp:TextBox ID="TextBox3" runat="server" Width="170px" required></asp:TextBox>
                    <br />
                </td>
            </tr>
            <tr>
                <td class="auto-style4">Product Description:</td>
                <td class="auto-style5">
                    <asp:TextBox ID="TextBox4" runat="server" Width="170px" required></asp:TextBox>
                    <br />
                </td>
            </tr>
            <tr>
                <td class="auto-style6"></td>
                <td class="auto-style7">
                    <asp:Button ID="Button1" runat="server" OnClick="Button1_Click" Text="Submit" Width="100px" />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                    <asp:Button ID="Button2" runat="server" Text="Reset" Width="66px" OnClick="Button2_Click" />
                    <br />
                    <br />
                    <asp:GridView ID="GridView1" runat="server" AutoGenerateColumns="False" BackColor="White" BorderColor="red" BorderStyle="None" BorderWidth="1px" CellPadding="4" DataKeyNames="ProductName" DataSourceID="SqlDataSource1">
                        <Columns>
                            <asp:CommandField ShowDeleteButton="True" ShowEditButton="True" />
                            <asp:BoundField DataField="ProductName" HeaderText="ProductName" ReadOnly="True" SortExpression="ProductName" />
                            <asp:BoundField DataField="ProductCategory" HeaderText="ProductCategory" SortExpression="ProductCategory" />
                            <asp:BoundField DataField="Quantity" HeaderText="Quantity" SortExpression="Quantity" />
                            <asp:BoundField DataField="Price" HeaderText="Price" SortExpression="Price" />
                            <asp:BoundField DataField="ProductDiscription" HeaderText="ProductDiscription" SortExpression="ProductDiscription" />
                        </Columns>
                        <FooterStyle BackColor="white" ForeColor="red" />
                        <HeaderStyle BackColor="white" Font-Bold="True" ForeColor="green" />
                        <PagerStyle BackColor="white" ForeColor="yellow" HorizontalAlign="Center" />
                        <RowStyle BackColor="White" ForeColor="black" />
                        <SelectedRowStyle BackColor="yellow" Font-Bold="True" ForeColor="blue" />
                        <SortedAscendingCellStyle BackColor="orange" />
                        <SortedAscendingHeaderStyle BackColor="black" />
                        <SortedDescendingCellStyle BackColor="#orange" />
                        <SortedDescendingHeaderStyle BackColor="#black" />
                    </asp:GridView>
                    <asp:SqlDataSource ID="SqlDataSource1" runat="server" ConnectionString="<%$ ConnectionStrings:CollegeConnectionString %>" DeleteCommand="DELETE FROM [ProductDetails] WHERE [ProductName] = @ProductName" InsertCommand="INSERT INTO [ProductDetails] ([ProductName], [ProductCategory], [Quantity], [Price], [ProductDiscription]) VALUES (@ProductName, @ProductCategory, @Quantity, @Price, @ProductDiscription)" SelectCommand="SELECT * FROM [ProductDetails]" UpdateCommand="UPDATE [ProductDetails] SET [ProductCategory] = @ProductCategory, [Quantity] = @Quantity, [Price] = @Price, [ProductDiscription] = @ProductDiscription WHERE [ProductName] = @ProductName">
                        <DeleteParameters>
                            <asp:Parameter Name="ProductName" Type="String" />
                        </DeleteParameters>
                        <InsertParameters>
                            <asp:Parameter Name="ProductName" Type="String" />
                            <asp:Parameter Name="ProductCategory" Type="String" />
                            <asp:Parameter Name="Quantity" Type="Decimal" />
                            <asp:Parameter Name="Price" Type="Decimal" />
                            <asp:Parameter Name="ProductDiscription" Type="String" />
                        </InsertParameters>
                        <UpdateParameters>
                            <asp:Parameter Name="ProductCategory" Type="String" />
                            <asp:Parameter Name="Quantity" Type="Decimal" />
                            <asp:Parameter Name="Price" Type="Decimal" />
                            <asp:Parameter Name="ProductDiscription" Type="String" />
                            <asp:Parameter Name="ProductName" Type="String" />
                        </UpdateParameters>
                    </asp:SqlDataSource>
                    <br />
                </td>
            </tr>
        </table>
    
    </div>
    </form>
</body>
</html>
