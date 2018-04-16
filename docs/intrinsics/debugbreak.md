---
title: "_ _debugbreak |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __debugbreak_cpp
- __debugbreak
dev_langs:
- C++
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e9aa50ee6cf450276dce70bfa38162a2f6392ed
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="debugbreak"></a>__debugbreak
**Microsoft 固有の仕様**  
  
 コードのブレークポイントを発生させます。ここで、デバッガーを実行するように求めるメッセージがユーザーに表示されます。  
  
## <a name="syntax"></a>構文  
  
```  
void __debugbreak();  
```  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|Header|  
|---------------|------------------|------------|  
|`__debugbreak`|x86、ARM、 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h>|  
  
## <a name="remarks"></a>コメント  
 `__debugbreak`コンパイラと同様、組み込み[DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297.aspx)ブレークポイントが発生する移植可能な Win32 方法は、します。  
  
> [!NOTE]
>  コンパイルするときに**/clr**、関数を含む`__debugbreak`は MSIL にコンパイルされます。 `asm int 3` により、関数がネイティブにコンパイルされます。 詳細については、次を参照してください。 [_ _asm](../assembler/inline/asm.md)です。  
  
 例:  
  
```  
main() {  
   __debugbreak();  
}  
```  
  
 上記のコードは、以下と似ています。  
  
```  
main() {  
   __asm {  
      int 3  
   }  
}  
```  
  
 このコードは x86 コンピューターにあります。  
  
 このルーチンは、組み込みとしてのみ使用できます。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [キーワード](../cpp/keywords-cpp.md)