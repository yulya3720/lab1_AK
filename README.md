# lab1_AK
## Лихацька Юлія, ІВ-82
## Лістинг
### calculator.cpp
```
#include "calculator.h"
int Calculator::Add (double a, double b)
{
	return a + b + 0.5;
}

int Calculator::Sub (double a, double b)
{
    return Add (a, -b);
}

int Calculator::Mul (double a, double b)
{
    return a * b + 0.5;
}
```
### calculator.h
```
#ifndef CALCULATOR_H
#define CALCULATOR_H

class Calculator
{
    public:
        int Add (double, double);
        int Sub (double, double);
        int Mul (double, double);
};

#endif
```

## Патчі
### 0001-fix-truncation-error.patch
```
From c37f5cfc33ffc0353d1efa9e007469f7f532caa2 Mon Sep 17 00:00:00 2001
From: Sergii Piatakov <sergii.piatakov@globallogic.com>
Date: Thu, 15 Nov 2018 15:28:04 +0200
Subject: [PATCH 1/2] fix truncation error

To convert float to integer the truncation is performed, but the
rounding is expected.

Test: Add (4.9, 4.9) should return 10.
Signed-off-by: Sergii Piatakov <sergii.piatakov@globallogic.com>
---
 calculator.cpp | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

diff --git a/calculator.cpp b/calculator.cpp
index b91afea..d93e35b 100644
--- a/calculator.cpp
+++ b/calculator.cpp
@@ -2,7 +2,7 @@
 
 int Calculator::Add (double a, double b)
 {
-    return a + b;
+	return a + b + 0.5;
 }
 
 int Calculator::Sub (double a, double b)
-- 
2.26.0.windows.1
```
### 0002-formatting-use-tabs-instead-of-spaces.patch
```
From 10fe534261f96373d58c0b9368c7039c647fd8ee Mon Sep 17 00:00:00 2001
From: Sergii Piatakov <sergii.piatakov@globallogic.com>
Date: Thu, 15 Nov 2018 15:26:35 +0200
Subject: [PATCH 2/2] formatting: use tabs instead of spaces

Signed-off-by: Sergii Piatakov <sergii.piatakov@globallogic.com>
---
 calculator.cpp | 4 ++--
 calculator.h   | 6 +++---
 2 files changed, 5 insertions(+), 5 deletions(-)

diff --git a/calculator.cpp b/calculator.cpp
index d93e35b..f323e14 100644
--- a/calculator.cpp
+++ b/calculator.cpp
@@ -2,10 +2,10 @@
 
 int Calculator::Add (double a, double b)
 {
-	return a + b + 0.5;
+	return a + b;
 }
 
 int Calculator::Sub (double a, double b)
 {
-    return Add (a, -b);
+	return Add (a, -b);
 }
diff --git a/calculator.h b/calculator.h
index 3740907..d59d596 100644
--- a/calculator.h
+++ b/calculator.h
@@ -3,9 +3,9 @@
 
 class Calculator
 {
-    public:
-        int Add (double, double);
-        int Sub (double, double);
+	public:
+		int Add (double, double);
+		int Sub (double, double);
 };
 
 #endif//CALCULATOR_H
-- 
2.26.0.windows.1
```
### Висновки
Під час виконання роботи була ознайомлена з системою контролю версій git та деякими її командами.
