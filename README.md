# NotWorking
a simple template working locally but NOT online

This simple Blazor WebApp Template has little modification.
it DOESN'T WORK when put online on a Subdirectory domain like
https://YourDomain.com/SubDir

it does work with "some" problem locally though

the modification to Microsoft template are as follow:

1. in App.razor, change baseRef to /Subdir/
	base href="/Subdir/"

2. Change Program.cs
	var app = builder.Build();
	app.UsePathBase("/Subdir");
	app.UseAuthentication();
	app.UseAuthorization();

3. Before app.UseAntiforgery();
	app.UseHttpsRedirection();
	app.UseStaticFiles();
	app.UseRouting();

Optional (for local test) it is still NOT working even if you don't include this
4. launchSettings.json
	"launchUrl": "SubDir/"
