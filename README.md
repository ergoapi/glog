# Usage

```bash
go get -u github.com/ergoapi/glog
```

## 使用

```bash
newLogger := glog.New(zlog.Zlog, viper.GetBool("db.debug"))
dbname := viper.GetString("db.name")
dsn := viper.GetString("db.dsn")
db, err := gorm.Open(mysql.Open(dsn), &gorm.Config{
  Logger:         newLogger,
  NamingStrategy: schema.NamingStrategy{SingularTable: true},
 })
```
