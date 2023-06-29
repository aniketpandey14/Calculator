     |---------------------------------------------------------- Backend Source Code ----------------------------------------------|
                                                                (  calculator.aspx.cs   )
using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;
using System.Web.UI;
using System.Web.UI.WebControls;

namespace sample3.samples
{
    public partial class Calculator : System.Web.UI.Page
    {
        static string option = "";
        int result;
        int num1 = 0; 
        int num2 = 0;
     
       protected void Page_Load(object sender, EventArgs e)
        {
           
        }

        protected void Button1_Click(object sender, EventArgs e)
        {
            output.Text = output.Text+ "1";
        }

        protected void Button2_Click(object sender, EventArgs e)
        {
            output.Text = output.Text+ "2";
        }

        protected void Button3_Click(object sender, EventArgs e)
        {
            output.Text = output.Text + "3";
        }

        protected void Button4_Click(object sender, EventArgs e)
        {
            output.Text = output.Text + "4";
        }

        protected void Button5_Click(object sender, EventArgs e)
        {
            output.Text = output.Text + "5";
        }

        protected void Button6_Click(object sender, EventArgs e)
        {
            output.Text = output.Text + "6";
        }

        protected void Button7_Click(object sender, EventArgs e)
        {
            output.Text = output.Text + "7";
        }

        protected void Button8_Click(object sender, EventArgs e)
        {
            output.Text = output.Text + "8";
        }

        protected void Button9_Click(object sender, EventArgs e)
        {
            output.Text = output.Text + "9";
        }
        protected void Button10_Click(object sender, EventArgs e)
        {
            output.Text = output.Text + "0";
        }

        protected void Button11_Click(object sender, EventArgs e)
        {
            option = "+";
            hide.Value = output.Text;
            output.Text = "";
        }

        protected void Button22_Click(object sender, EventArgs e)
        {
            option = "-";
            hide.Value = output.Text;
            output.Text = "";
        }

        protected void Button33_Click(object sender, EventArgs e)
        {
            option = "*";
            hide.Value = output.Text;
            output.Text = "";
        }

        protected void Button12_Click(object sender, EventArgs e)
        {
            output.Text = "";
            num1 = 0;
            num2 = 0;
            result = 0;
            Exception.Text = "";
        }
        protected void Button13_Click(object sender, EventArgs e)
        {
            option = "/";
            hide.Value = output.Text;
            output.Text = "";
        }

        protected void Button14_Click(object sender, EventArgs e)
        {
            num1 =Convert.ToInt32( hide.Value);
            num2 = Convert.ToInt32(output.Text);

            if (option == ("+"))
            {
                result = (num1 + num2);
            }
            if(option == ("-"))
            {
                result = (num1 - num2);
            }
            if (option == ("*"))
            {
                result = (num1 * num2);
            }
            if (option == ("/"))
            {  
                if(num2==0)
                {
                    Exception.Text = "Cannot divide by 0";
                }
                else
                {
                    result = (num1 / num2);
                }
            }
           

            output.Text = Convert.ToString(result);

            //switch(option)
            //{
            //    case "+":
            //        result = Convert.ToString(num1 + num2);
            //        output.Text = result;
            //        break;
            //    case "-":
            //        result = Convert.ToString(num1 + num2);
            //        break;
            //    case "*":
            //        result = Convert.ToString(num1 + num2);
            //        break;
            //    case "/":
            //        result = Convert.ToString(num1 + num2);
            //        break;

            //}


        }
    }
}






|________________________________________________FrontEnd Coding_____________________________________________________________|


<%@ Page Title="" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Calculator.aspx.cs" Inherits="sample3.samples.Calculator" %>
<asp:Content ID="Content1" ContentPlaceHolderID="MainContent" runat="server">

    <asp:Label ID="output" runat="server" Text=""></asp:Label> <br />
    <%--<input type="hidden" id="hide" />--%>
    <asp:HiddenField ID="hide" runat="server" />

    <asp:Button ID="Button1" runat="server" Text="1" OnClick="Button1_Click" Height="26px" Width="50px"  />
    <asp:Button ID="Button2" runat="server" Text="2" OnClick="Button2_Click" Width="50px" />
    <asp:Button ID="Button3" runat="server" Text="3" OnClick="Button3_Click" Width="50px"/>  
    <asp:Button ID="Button11" runat="server" Text="+" Width="50px" OnClick="Button11_Click" />  <br />


    <asp:Button ID="Button4" runat="server" Text="4" OnClick="Button4_Click" Width="50px" />
    <asp:Button ID="Button5" runat="server" Text="5" OnClick="Button5_Click" Width="50px" />
    <asp:Button ID="Button6" runat="server" Text="6" OnClick="Button6_Click" Height="26px" Width="50px" /> 
     <asp:Button ID="Button22" runat="server" Text="-" Width="50px" OnClick="Button22_Click" />  <br />


    <asp:Button ID="Button7" runat="server" Text="7" OnClick="Button7_Click" Width="50px" />
    <asp:Button ID="Button8" runat="server" Text="8" OnClick="Button8_Click" Width="50px" />
    <asp:Button ID="Button9" runat="server" Text="9" OnClick="Button9_Click" style="width: 50px" /> 
    <asp:Button ID="Button33" runat="server" Text="*" Width="50px" OnClick="Button33_Click" />  <br />

    <asp:Button ID="Button10" runat="server" Text="0" OnClick="Button10_Click" Width="50px" />
    <asp:Button ID="Button12" runat="server" Text="C" OnClick="Button12_Click" Width="50px" />
    <asp:Button ID="Button13" runat="server" Text="/" OnClick="Button13_Click" Width="50px" />
    <asp:Button ID="Button14" runat="server" Text="=" OnClick="Button14_Click" Width="50px" />  <br />


    <asp:Label ID="Exception" runat="server" ForeColor="Red" ></asp:Label>

</asp:Content>
