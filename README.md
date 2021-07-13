
# A simple terminal progress bar

Made with a single c++ class, which you always wanted. Avoids redundant update by utilising [ANSI escape codes](https://gist.github.com/fnky/458719343aabd01cfb17a3a4f7296797#file-ansi-md).

## Usage

```cpp
int main()
{
    Bar b(20);                 // creates a progress bar in terminal of width 20 (excluding the braces)

    for(int i = 1; i <= 1000000; i++)
    {
        int p = (float)i / 1000000 * 100;
        b.update(p);            // increments the bar as per the percentage value passed(0-100).
        if(p > 10) b.finish();  // won't be updated once this is executed.
    }
}
```
## Don'ts
Do not print anything before calling the finish or until the bar object goes out of scope.
## Contributions
You can use the above mentioned ANSI escape codes to change the color, font style, etc..

## License
[MIT](https://choosealicense.com/licenses/mit/)
