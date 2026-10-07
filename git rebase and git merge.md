### `git merge`

كيجمع تاريخ جوج branches، ولكن **ماشي بالضرورة** كيخلق خط متشعب.

مثلاً ممكن يكون:

```
A---B---C---D
```

إلا كان **Fast-Forward merge**.

أما إلا كانو بجوج فيهم commits مختلفين:

```
      D---E
     /     \
A---B-------M
     \     /
      C---F
```

هنا `merge` يقدر يصاوب **merge commit** وكيبقى التاريخ فيه branches متفرعين.

### `git rebase`

كيشد commits ديال branch وكيـ**عاود يطبقهم فوق آخر commit** ديال base:

```
قبل:
A---B---C main
     \
      D---E feature

بعد rebase:
A---B---C---D'---E' feature
```

يعني كيعطي **تاريخ خطي (linear history)** فهاد الحالة.