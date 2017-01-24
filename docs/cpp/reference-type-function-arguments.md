---
title: "参照型関数の引数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "引数 [C++], 関数"
  - "関数の引数, 参照の種類"
  - "関数パラメーター, 参照の種類"
  - "関数 [C++], パラメーター"
  - "渡す (パラメーターを), 参照型の引数"
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 参照型関数の引数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

多くの場合、大きなオブジェクトよりも、関数への参照を渡す方が効率的です。  これにより、コンパイラは、オブジェクトへのアクセスに使用される構文を保持しつつ、オブジェクトのアドレスを渡すことができます。  `Date` 構造体を使用する次の例について考えます。  
  
```  
// reference_type_function_arguments.cpp  
struct Date  
{  
short DayOfWeek;  
short Month;  
short Day;  
short Year;  
};  
  
// Create a Julian date of the form DDDYYYY  
// from a Gregorian date.  
long JulianFromGregorian( Date& GDate )  
{  
static int cDaysInMonth[] = {  
31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31  
   };  
long JDate = 0;  
// Add in days for months already elapsed.  
for ( int i = 0; i < GDate.Month - 1; ++i )  
JDate += cDaysInMonth[i];  
// Add in days for this month.  
JDate += GDate.Day;  
  
// Check for leap year.  
if ( GDate.Year % 100 != 0 && GDate.Year % 4 == 0 )  
JDate++;  
// Add in year.  
JDate *= 10000;  
JDate += GDate.Year;  
  
return JDate;  
}  
  
int main()  
{  
}  
```  
  
 前のコードは、参照によって渡された構造体のメンバーは、ポインター メンバー選択演算子 \(**\-\>**\) ではなく、メンバー選択演算子 \(**.**\) を使用してアクセスされることを示しています。  
  
 参照型として渡された引数はポインター型以外の型の構文に従いますが、**const** として宣言されない限り変更できるという、ポインター型の 1 つの重要な特性を保持します。  前のコードの意図は `GDate` オブジェクトを変更することではないため、より適切な関数プロトタイプは次のとおりです。  
  
```  
long JulianFromGregorian( const Date& GDate );  
```  
  
 このプロトタイプによって、関数 `JulianFromGregorian` が引数を変更しないことが保証されます。  
  
 参照型を受け取るようにプロトタイプ宣言された関数は、*typename* から *typename***&** に標準で変換されるため、参照型の代わりに同じ型のオブジェクトを受け取ることができます。  
  
## 参照  
 [参照](../cpp/references-cpp.md)