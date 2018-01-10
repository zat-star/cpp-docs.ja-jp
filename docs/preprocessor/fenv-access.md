---
title: "fenv_access |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
dev_langs: C++
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 623c9cb9af1d7df137aa7ee92071e34ad99a6331
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fenvaccess"></a>fenv_access
フラグ テストとモード変更を変える可能性のある最適化を無効 (ON) または有効 (OFF) にします。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma fenv_access [ON | OFF]  
```  
  
## <a name="remarks"></a>コメント  
 既定では、`fenv_access` は OFF です。  
  
 浮動小数点の動作の詳細については、次を参照してください。 [/fp (浮動小数点の動作を指定)](../build/reference/fp-specify-floating-point-behavior.md)です。  
  
 `fenv_access` の影響を受ける最適化の種類は次のとおりです。  
  
-   グローバルの共通部分式の削除  
  
-   コードの移動  
  
-   定数の折りたたみ  
  
 その他の浮動小数点プラグマには以下があります。  
  
-   [float_control](../preprocessor/float-control.md)  
  
-   [fp_contract](../preprocessor/fp-contract.md)  
  
## <a name="example"></a>例  
  
```  
// pragma_directive_fenv_access_x86.cpp  
// compile with: /O2  
// processor: x86  
#include <stdio.h>  
#include <float.h>   
#include <errno.h>  
#pragma fenv_access (on)  
  
int main() {  
   double z, b = 0.1, t = 0.1;  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);  
   if (err != 0) {  
      printf_s("The function _controlfp_s failed!\n");  
      return -1;  
   }  
   z = b * t;  
   printf_s ("out=%.15e\n",z);  
}  
```  
  
```Output  
out=9.999999776482582e-003  
```  
  
## <a name="example"></a>例  
 次のサンプルは、Itanium プロセッサ用の出力ファイルを作成するコンパイラ用です。 **/fp: 正確な**手動で計算した場合と同様に、大きい値 FLT_MAX (3.402823466 e + 38 f) を計算するよりも、その結果として sum が 1.0 結果は、拡張精度内に中間結果を保持します。 **/fp: 厳密な**最初の加算生成無限大の場合は、式全体で保持するために中間は、ソース精度 (float) で結果を保持します。  
  
```  
// pragma_directive_fenv_access_IPF.cpp  
// compile with: /O2 /fp:precise  
// processor: IPF  
// compiling with /fp:precise prints 1.0F  
// compile with /fp:strict to print infinity  
  
#include <stdio.h>  
float arr[5] = {3.402823465e+38F,   
               3.402823462e+38F,  
               3.402823464e+38F,  
               3.402823463e+38F,  
               1.0F};  
  
int main() {  
   float sum = 0;  
   sum = arr[0] + arr[1] - arr[2] - arr[3] + arr[4];  
   printf_s("%f\n", sum);  
}  
```  
  
```Output  
1.000000  
```  
  
## <a name="example"></a>例  
 前の例の `#pragma fenv_access (on)` をコメント アウトすると、コンパイラがコンパイル時に評価し、その場合、制御モードが使用されないため、出力が異なることに注意してください。  
  
```  
// pragma_directive_fenv_access_2.cpp  
// compile with: /O2  
#include <stdio.h>  
#include <float.h>   
  
int main() {  
   double z, b = 0.1, t = 0.1;  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);  
   if (err != 0) {  
      printf_s("The function _controlfp_s failed!\n");  
      return -1;  
   }  
   z = b * t;  
   printf_s ("out=%.15e\n",z);  
}  
```  
  
```Output  
out=1.000000000000000e-002  
```  
  
## <a name="see-also"></a>参照  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)