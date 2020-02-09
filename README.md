# Code-based migration

Open Package Manager Console in Visual Studio and run:
- `Enable-Migrations`
- `Add-Migration <NAME>`
- `Update-Database` or use `Update-Database -script` to generate script and execute in DB

Example: Add manually `DropTable("dbo.Accounts");` to Up() method to drop the table.

```` cs
namespace EF.Migrations
{
    using System.Data.Entity.Migrations;
    
    public partial class DropOldReservationsTable : DbMigration
    {
        public override void Up()
        {
            DropTable("dbo.Accounts");
        }
        
        public override void Down()
        {
        }
    }
}
````


