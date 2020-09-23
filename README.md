<div align="center">

## C\# SMTP Mail Console


</div>

### Description

Send Mail by C# in console.

Simple view use of a class , properties (get/set)

you can test it by using .NET SDK framework

compile it with the csc command in console

c:> csc ClsMail.cs

after compiling it will give you the exe file
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Peter V\.](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/peter-v.md)
**Level**          |Beginner
**User Rating**    |5.0 (20 globes from 4 users)
**Compatibility**  |C\#
**Category**       |[Complete Applications](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/complete-applications__10-7.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/peter-v-c-smtp-mail-console__10-97/archive/master.zip)





### Source Code

<TABLE BORDER=1 CELLSPACING=0 CELLPADDING=2 BGCOLOR=#1FC0D0>
<TR><TD>
<TT><PRE>using System;
using System.Web.Mail;
namespace myMail
{
	/// &lt;summary&gt;
	/// Summary description for ClsStartup.
	/// &lt;/summary&gt;
	public class ClsMail
	{
		private string mTxtEmailTo;     // Emailaddres for user to send
		private string mTxtEmailFrom;    // Emailaddres for user from
		private string mTxtMailSubj;
		private string mTxtMailBody;
		private string mTxtServerName;
		public ClsMail()
		{
			Console.WriteLine (&quot;Console SMTP Mail V0.1&quot;);
			Console.WriteLine (&quot;----------------------&quot;);
			mTxtEmailFrom = &quot;&quot;;
			mTxtEmailTo = &quot;&quot;;
		}
		public string SmtpServer
		{
			set
			{
				mTxtServerName = value;
				SmtpMail.SmtpServer = value;
			}
			get
			{
				return mTxtServerName;
			}
		}
		public string EmailFrom
		{
			set
			{
				mTxtEmailFrom = value;
			}
			get
			{
				return mTxtEmailFrom;
			}
		}
		public string EmailTo
		{
			set
			{
				mTxtEmailTo = value;
			}
			get
			{
				return mTxtEmailTo;
			}
		}
		public string MailBody
		{
			set
			{
				mTxtMailBody = value;
			}
			get
			{
				return mTxtMailBody;
			}
		}
		public string MailSubject
		{
			set
			{
				mTxtMailSubj = value;
			}
			get
			{
				return mTxtMailSubj;
			}
		}
		public bool SendNow()
		{
			try
			{
				Console.WriteLine();
				Console.WriteLine(&quot;Connecting to : {0}&quot; , mTxtServerName);
				SmtpMail.Send (mTxtEmailFrom,mTxtEmailTo,mTxtMailSubj,
											 mTxtMailBody);
			 return true;
			}
			catch (Exception e)
			{
				Console.WriteLine(&quot;Error Mail Sending : {0}&quot; , e.Message );
				return false;
			}
		}
		/// &lt;summary&gt;
		/// Startup Method
		/// &lt;/summary&gt;
		[STAThread]
		static void Main(string[] args)
		{
			/// Header MainApplication
		ClsMail Smtp = new ClsMail();
		Console.Write(&quot;Smtp server : &quot;);
		Smtp.SmtpServer = Console.ReadLine();
		Console.Write(&quot;Your Emailaddr : &quot;);
		Smtp.EmailFrom = Console.ReadLine();
		Console.Write(&quot;Email To Send : &quot;);
		Smtp.EmailTo = Console.ReadLine();
		Console.Write(&quot;Subject Mail : &quot;);
		Smtp.MailSubject = Console.ReadLine();
		Console.Write(&quot;Body : &quot;);
		Smtp.MailBody = Console.ReadLine();
			if (Smtp.SendNow())
			{
				Console.WriteLine(&quot;End Session : Succesfully&quot;);
			}
			else
			{
				Console.WriteLine(&quot;End Session : Failed&quot;);
			}
		Console.WriteLine(&quot;Press any Key&quot;);
		Console.Read();
		}
	}
}</PRE></TT>
</TD></TR>
</TABLE>

