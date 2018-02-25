---
title: "float_control |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
dev_langs:
- C++
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1525b92b43a688cdec970c646613aa4474d44cc3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="floatcontrol"></a>float_control
関数の浮動小数点動作を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
float_control( value,setting [push] | push | pop )  
```  
  
## <a name="flags"></a>フラグ  
 `value`, `setting` **[push]**  
 浮動小数点の動作を指定します。 `value` 指定できます**正確な**または**を除く**です。 詳細については、「[/fp (浮動小数点の動作の指定)](../build/reference/fp-specify-floating-point-behavior.md)」を参照してください。 `setting` いずれかを指定できます**で**または**オフ**です。  
  
 場合`value`は**正確な**の設定**正確な**と**を除く**が指定されています。 **除く**にのみ設定できます**で**とき**正確な**にも設定されている**で**です。  
  
 場合、省略可能な**プッシュ**トークンを追加する、現在の設定`value`を内部コンパイラ スタックにプッシュします。  
  
 **push**  
 現在の `float_control` 設定を内部コンパイラ スタックにプッシュします。  
  
 **pop**  
 削除、`float_control`内部コンパイラ スタックの一番上から設定およびようにするが、新しい`float_control`設定します。  
  
## <a name="remarks"></a>コメント  
 有効にすることはできません`float_control precise`ときはオフ**を除く**にします。 同様に、**正確な**ときにオフにすることはできません`fenv_access`にします。 `float_control` プラグマを使用して厳格なモデルから高速モデルに移行するには、次のコードを使用します。  
  
```  
#pragma float_control(except, off)  
#pragma fenv_access(off)  
#pragma float_control(precise, off)  
// The following line is needed on Itanium processors  
#pragma fp_contract(on)  
```  
  
 `float_control` プラグマを使用して高速モデルから厳格なモデルに移行するには、次のコードを使用します。  
  
```  
#pragma float_control(precise, on)  
#pragma fenv_access(on)  
#pragma float_control(except, on)  
// The following line is needed on Itanium processors.  
#pragma fp_contract(off)  
```  
  
 その他の浮動小数点プラグマには以下があります。  
  
-   [fenv_access](../preprocessor/fenv-access.md)  
  
-   [fp_contract](../preprocessor/fp-contract.md)  
  
## <a name="example"></a>例  
 次のサンプルは、`float_control` プラグマを使用してオーバーフロー浮動小数点例外をキャッチする方法を示しています。  
  
```  
// pragma_directive_float_control.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <float.h>  
  
double func( ) {  
   return 1.1e75;  
}  
  
#pragma float_control (except,on)  
  
int main( ) {  
   float u[1];  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, ~_EM_OVERFLOW, _MCW_EM);  
   if (err != 0)  
      printf_s("_controlfp_s failed!\n");  
  
   try  {  
      u[0] = func();  
      printf_s ("Fail");     
      return(1);  
   }   
  
   catch (...)  {  
      printf_s ("Pass");  
      return(0);  
   }  
}  
```  
  
```Output  
Pass  
```  
  
## <a name="see-also"></a>参照  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)