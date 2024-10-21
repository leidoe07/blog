# Daring Debugging: Fixing Python Code One Bug at a Time

Debugging code isn’t exactly what I’d call a fun time. Let’s be real — when you’re just starting out with Python, it can feel like the language is actively working against you. But when you do manage to figure out what’s broken, it’s one of those “light bulb over the head” moments that makes the struggle worth it.

For this assignment, I had to go through a bunch of Python code snippets, spot what was wrong, and fix them. Spoiler: some of these bugs were easy to miss, but I got there in the end.

---

## 1. Temperature Check Gone Wrong
The first bit of code was supposed to tell you if it was hot, temperate, or cold outside. Sounds easy enough, right? Well, not when the code ignores an entire range of temperatures like it’s no big deal.

**Original Code**:
```python
temperature = 75

if temperature > 80:
    print("It's hot")
elif temperature > 50:
    print("It's temperate")
elif temperature < 0:
    print("It's cold")
