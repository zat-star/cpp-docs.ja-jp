---
title: noreturn |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
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
ms.workload:
- cplusplus
ms.openlocfilehash: 15df38143ded836b671fdfa17a7c5790a9fe960a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="see-also"></a>参照  
 [_ _declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)