# Why character array is better than String for Storing password in Java?


### Both Character array and String can be used to store text data but choosing one over other is difficult question if you haven't faced the situation already.



Answer:

---
  
1. Since Strings are immutable in Java if you store password as plain text it will be available in memory until Garbage collector clears it and since String are used in String pool for reusability there is pretty high chance that it will be remain in memory for long duration, which pose a security threat. Since any one who has access to memory dump can find the password in clear text and that's another reason you should always used an encrypted password than plain text. Since Strings are immutable there is no way contents of Strings can be changed because any change will produce new String, while if you char[] you can still set all his element as blank or zero. So Storing password in character array clearly mitigates security risk of stealing password.

2. Java itself recommends using getPassword() method of JPasswordField which returns a char[] and deprecated getText() method which returns password in clear text stating security reason. Its good to follow advice from Java team and adhering to standard rather than going against it.

3. With String there is always a risk of printing plain text in log file or console but if use Array you won't print contents of array instead its memory location get printed. though not a real reason but still make sense.

```Java
String strPassword="Unknown";
char[] charPassword= new char[]{'U','n','k','w','o','n'};
System.out.println("String password: " + strPassword);
System.out.println("Character password: " + charPassword);
```
*Output:*  
`String password: Unknown`  
`Character password: [C@110b053`

---

__Contrary:__  

```Java
public class printPwd {
public static void main(String[] args) {
String strPassword = "Unknown";
char[] charPassword = new char[] { 'U', 'n', 'k', 'n', 'o', 'w', 'n' };
System.out.println("String password: " + strPassword);
System.out.println("Character password: " + String.valueOf(charPassword));
}
}
```

*Output:*  
`String password: Unknown`  
`Character password: Unknown`  

---

### Using char[] instead of String for passwords is a bad idea for a few reasons:

1. That's going to massively complicate things. Strings maintain information about character encodings - char[] {obviously} does not. So if you use char[], you have to be very careful to always use the same encoding. This is critical if you support non-US English users (and you should always do that!).

2. If a malicious user gets access to read core dump files in /tmp, it's game over anyways. At that point, it means that not only has a malicious user gained access to your server, but he's also gained either root or application user access - so he's fully compromised the system.

3. char[] are not pinned to RAM. The OS swaps char[] data just as easily as String data, writing it to disk in the swap file.

4. Strings may be immutable, making it more likely that they hang around for a while in memory due to string internment, but char[]'s aren't guaranteed to be removed from memory either due to the uncertainties of garbage collections. You can never be sure any memory is cleared in Java, nor can you tell Java to clear any memory.  

Using char[] instead of String makes your code buggier, harder to maintain, harder to write, and only more secure in a totally impractical sense.

---

Here, the main thing to know is that the String is Serializable; so are arrays. Hence it becomes difficult to decide what a user should choose char[] or String to store password.  

**_What do you choose?_**
=========================