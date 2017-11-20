---
title: "サンプル呼び出しの結果 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 960dab7458af70d79fbcbc575e2fcd0e5678c3c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="results-of-calling-example"></a>サンプル呼び出しの結果
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
  
## <a name="cdecl"></a>__cdecl  
 C の装飾された関数名は "_MyFunc" です。  
  
 ![CDECL 呼び出し規約](../cpp/media/vc37i01.gif "vc37I01")  
__cdecl の呼び出し規則  
  
## <a name="stdcall-and-thiscall"></a>__stdcall と thiscall  
 C の装飾名 (`__stdcall`) は"_MyFunc@20"。 C++ の装飾名は商標で守られています。  
  
 ![&#95; &#95; stdcall と thiscall の呼び出し規約](../cpp/media/vc37i02.gif "vc37I02")  
__stdcall と thiscall の呼び出し規則  
  
## <a name="fastcall"></a>__fastcall  
 C の装飾名 (`__fastcall`) は"@MyFunc@20"。 C++ の装飾名は商標で守られています。  
  
 ![呼び出し規約 &#95; &#95; fastcall](../cpp/media/vc37i03.gif "vc37I03")  
__fastcall の呼び出し規則  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [呼び出しの例: 関数プロトタイプと呼び出し](../cpp/calling-example-function-prototype-and-call.md)