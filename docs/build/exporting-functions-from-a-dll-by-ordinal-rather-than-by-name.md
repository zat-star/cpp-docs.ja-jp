---
title: "名前ではなく序数値による DLL 関数のエクスポート | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "NONAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "エクスポート (DLL を) [C++], 序数値"
  - "エクスポート (関数を) [C++], 序数値"
  - "NONAME 属性"
  - "序数エクスポート [C++]"
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 名前ではなく序数値による DLL 関数のエクスポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL 関数の最も簡単なエクスポート方法は、名前によるエクスポートです。  たとえば、**\_\_declspec\(dllexport\)** では名前を使用します。  ただし、関数は序数値でもエクスポートできます。  この場合は、**\_\_declspec\(dllexport\)** の代わりに、.def ファイルを使用します。  関数の序数値を指定するには、.def ファイルで関数名にこの序数値を続けます。  序数値の指定方法については、「[DEF ファイルを使った DLL からのエクスポート](../build/exporting-from-a-dll-using-def-files.md)」を参照してください。  
  
> [!TIP]
>  DLL のファイル サイズを最適化するには、各エクスポート関数に対して **NONAME** 属性を使用します。  **NONAME** 属性を指定すると、関数名ではなく序数値が、DLL のエクスポート テーブルに格納されます。  特にエクスポートする関数が多い場合、メモリが相当量節約されます。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [.def ファイルを使った DLL からのエクスポート](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\) を使った DLL からのエクスポート](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
## 参照  
 [DLL からのエクスポート](../build/exporting-from-a-dll.md)