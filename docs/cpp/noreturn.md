---
title: "noreturn |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- noreturn_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 45de52c2c3c0b60a62bf19e38854c53e841ed500
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="noreturn"></a>noreturn
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 この `__declspec` 属性は、コンパイラに、関数が戻らないことを示します。 その結果、コンパイラで認識されるへの呼び出しに続くコード、 **__declspec(noreturn)**関数に到達できません。  
  
 コンパイラで値を返さないコントロール パスの関数が検出されると、警告 (C4715) またはエラー メッセージ (C2202) が生成されます。 使用することができますを返すことはありません関数のためのコントロール パスに到達できない場合**__declspec(noreturn)**この警告やエラーを防ぐためです。  
  
> [!NOTE]
>  追加**__declspec(noreturn)**を返すと予想される関数への未定義の動作になります。  
  
## <a name="example"></a>例  
 次の例で、 **else**句に return ステートメントが含まれていません。  宣言`fatal`として**__declspec(noreturn)**エラーまたは警告メッセージを回避できます。  
  
```  
// noreturn2.cpp  
__declspec(noreturn) extern void fatal () {}  
  
int main() {  
   if(1)  
     return 1;  
   else if(0)  
     return 0;  
   else  
     fatal();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [_ _declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)
