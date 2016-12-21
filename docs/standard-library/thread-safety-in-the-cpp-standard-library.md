---
title: "C++ 標準ライブラリ内のスレッド セーフ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "標準 C++ ライブラリ, スレッド セーフ"
  - "スレッド セーフ"
  - "スレッド セーフ, 標準テンプレート ライブラリ"
ms.assetid: 9351c8fb-4539-4728-b0e9-226e2ac4284b
caps.latest.revision: 21
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C++ 標準ライブラリ内のスレッド セーフ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のスレッド セーフの規則は標準 C\+\+ ライブラリのすべてのクラスに適用されます。これには、次に示すように `shared_ptr` が含まれます。  場合によっては、より強力な保証が提供されます。たとえば、以下に示すような標準の iostream オブジェクトや、[\<atomic\>](../standard-library/atomic.md) 内の型のようなマルチスレッド専用の型があります。  
  
 オブジェクトは、複数のスレッドからの読み取りに対してスレッド セーフです。  たとえば、オブジェクト A が指定された場合、スレッド 1 とスレッド 2 から A の同時読み取りを安全に行うことができます。  
  
 あるオブジェクトに対して 1 つのスレッドが書き込みを行っている場合、同じスレッドまたは別のスレッドでのそのオブジェクトに対する読み取りと書き込みはすべて保護される必要があります。  たとえば、オブジェクト A が指定され、スレッド 1 が A に書き込みを行っている場合、スレッド 2 で A の読み取りや書き取りを行えないようにする必要があります。  
  
 ある型の 1 つのインスタンスに対して読み取りや書き込みを行うのが安全です。これは、別のスレッドが同じ型の別のインスタンスに対して読み取りまたは書き込みを行っている場合でもそうです。  たとえば、同じ型のオブジェクト A と B が指定されている場合、A がスレッド 1 で書き込まれ、B がスレッド 2 で読み取られている場合は安全です。  
  
## shared\_ptr  
 複数のスレッドで異なる [shared\_ptr](../standard-library/shared-ptr-class.md) オブジェクト \(所有権を共有するコピーである場合も含めて\) に対する読み取りと書き込みを同時に行うことができます。  
  
## iostream  
 標準の iostream オブジェクト `cin`、`cout`、`cerr`、`clog`、`wcin`、`wcout`、`wcerr`、および `wclog` は、他のクラスと同じ規則に従いますが、例外として、複数のスレッドからオブジェクトに安全に書き込むことができます。  たとえば、スレッド 1 はスレッド 2 と同時に [cout](../Topic/cout.md) に書き込むことができます。  ただし、2 つのスレッドからの出力が混ざる可能性があります。  
  
> [!NOTE]
>  ストリーム バッファーからの読み取りは、読み取り操作とは見なされません。  その代わりに、クラスの状態が変わるため、書き込み操作と見なされます。  
  
## 参照  
 [STL の概要](../standard-library/cpp-standard-library-overview.md)