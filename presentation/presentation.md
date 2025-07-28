
# Why Rust


# Borrowing



# Error checking in C
- convention: return 0 on success: 
- There are exceptions to the convention`strcmp(), fork(), malloc(), fopen(),...`

```C

int res = open(...);
if (!res) {
    // open failed
    return 1;
}
```
 

# Java in Theory
```java
public void loadData() {
    try {
        connect();
        readFile();
        parseData();
    } catch (IOException e) {
        System.err.println("File error: " + e.getMessage());
    } catch (SQLException e) {
        System.err.println("DB error: " + e.getMessage());
    } catch (DataException e) {
        System.err.println("Data error: " + e.getMessage());
    }
}
```
# Java in Practise

```Java
public void loadData() {
    try {
        connect();
        readFile();
        parseData();
    } catch (Exception e) {
        System.err.println("something broke lol");
    }
}
```


# Rust in Theory and Practice
```rust
fn load_data() -> Result<(), Box<dyn Error>> {
    connect()?;
    read_file()?;
    parse_data()?;
    Ok(())
}
```


# Sources

1. https://www.baeldung.com/java-exceptions   
