---
title: "コンパイラ エラー C3172 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3172
dev_langs:
- C++
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: a53e7bc0b8543813e5745773f6a7548eb9a83442
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="compiler-error-c3172"></a>コンパイラ エラー C3172
'モジュール名': プロジェクトで異なる idl_module の属性を指定することはできません  
  
 [idl_module](../../windows/idl-module.md)という同じ属性名しますが、異なる`dllname`または`version`パラメーターが 2 つのコンパイル時にファイルに見つかりませんでした。 1 つの一意なのみ`idl_module`コンパイルごとに属性を指定できます。  
  
 同じ`idl_module`属性は 1 つ以上のソース コード ファイルで指定できます。  
  
 たとえば場合、次`idl_module`属性が見つかりませんでした。  
  
```  
// C3172.cpp  
[module(name="MyMod")];  
[ idl_module(name="x", dllname="file.dll", version="1.1") ];  
int main() {}  
```  
  
 この場合、次のようになります。  
  
```  
// C3172b.cpp  
// compile with: C3172.cpp  
// C3172 expected  
[ idl_module(name="x", dllname="file.dll", version="1.0") ];  
```  
  
 c3172 (別のバージョンの値に注意してください)。
