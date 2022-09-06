# Roman Kurpachenko

## Software developer

---

## Contacts:
#### email: romankurpachenko@gmail.com
#### phone: +48 571-262-760
#### LinkedIn: [Roman Kurpachenko](https://www.linkedin.com/in/roman-kurpachenko/)
#### Telegram: [Roman Kurpachenko](https://t.me/romankurpachenko)

---

## About myself:

Hi)

I'm not really a novice developer, but I want to keep myself in good shape and do what I've been dreaming about for a long time - to establish a new development area for me

I am from Belarus, [Mogilev](https://goo.gl/maps/J5DJFpL4MJ88Cc5fA), but now I live in Poland, [Gdansk](https://goo.gl/maps/rMMqjsssU65g4qbF8).
If suddenly someone wants to visit the city - be sure to contact me and I'll help you with excursion!)

And in general, I also created training in my hometown, so I will be happy to help with any questions I can answer (and can't :D)

Started my career at EPAM in 2018 and finished BRU in 2020, Mogilev. Software engineer degree (ПИР-161)

---

## Skills:

Name | Level 
-|- 
.NET | Advanced
MS SQL | Intermediate
MongoDB | Intermediate
Oracle | Intermediate
Azure Cloud | Intermediate
Azure DevOps | Intermediate
AWS | Basic
GIT | Advanced
Agile | Advanced
Waterfall | Advanced
Software architecture | Basic
Security development | Intermediate
Security testing | Intermediate

---

## Code example:

```
public class EnigmaRotor
{
    private readonly string _pattern;
    
    private readonly string _alpha = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    
    private readonly int _notch1;
    
    private readonly int _notch2;
    
    private int _reelPosition = 0;
    
    private readonly int _rsl = 0;
    public enum Path
    {
        Fwd,
        Rev
    };
    public EnigmaRotor(
        Tuple<string, int, int> rotor, 
        int ringPos, 
        int startPos)
    {
        _pattern = rotor.Item1;
        _notch1 = rotor.Item2;
        _notch2 = rotor.Item3;
        _reelPosition = startPos;
        _rsl = ringPos;
    }
    public bool IsNotched => (_reelPosition == _notch1 || _reelPosition == _notch2);
    public void Rotate()
    {
        _reelPosition = (_reelPosition + 1) % 26;
    }
    public int Transpose(int x, Path dir)
    {
        x = (x + _reelPosition - _rsl + 26) % 26;
        
        var t = GetIndex(x, dir) - _reelPosition + _rsl + 26;
        
        return t % 26;
    }
    private int GetIndex(int x, Path dir)
    {
        if (dir == Path.Fwd)
        {
            return _alpha.IndexOf(_pattern[x]);
        }
        else
        {
            return _pattern.IndexOf(_alpha[x]);
        }
    }
}
```