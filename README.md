
# A simple terminal progress bar

Made with a single c++ class, which you always wanted.
Resizable bar.
Avoids redundant update by utilising [ANSI escape codes](https://gist.github.com/fnky/458719343aabd01cfb17a3a4f7296797#file-ansi-md).  
Instant flush without a newline.

## Usage

```cpp
int main()
{
    Bar b(20);                 // creates a progress bar in terminal of width 20 (excluding the braces)

    for(int i = 1; i <= 1000000; i++)
    {
        int p = (float)i / 1000000 * 100;
        b.update(p);            // increments the bar as per the percentage value passed(0-100).
    }
}
```
## Example

```cpp
int main()
{
    Bar b(20);
    for(int i = 1; i <= 100000; i++)
    {
        int p = (float)i / 100000 * 100;
        b.update(p);
        if (p > 10)
            b.finish();
    }
    b.finish(); // don't forget this before printing something else.

    Bar a(100);
    for (int i = 1; i <= 100000; i++)
    {
        int p = (float)i / 100000 * 100;
        a.update(p);
    }
}
```
## Output
![output screenshot](https://github.com/YoMF/image-assets/blob/0925f3d2286a2de7a455678b1d31579041a3591d/progress-bar-example.png)

## Don'ts
Do not print anything before calling the finish or until the bar object goes out of scope.

## Test Configurations:
- system :   Ubuntu 20.10 (64bit)  
- compiler:  g++  
- flags:     -std=c++20 -o3  

## Contributions
You can use the above mentioned ANSI escape codes to change the color, font style, etc..

## License
[MIT](https://github.com/YoMF/shared-assets/blob/d87d8748a96b587e84eaa4824520721698065e46/LICENSE)
