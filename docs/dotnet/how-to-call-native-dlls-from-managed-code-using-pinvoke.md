---
title: "方法: PInvoke を使用してマネージ コードからネイティブ Dll を呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- platform invoke [C++], calling native DLLs
- interop [C++], calling native DLLs
- marshaling [C++], calling native DLLs
- data marshaling [C++], calling native DLLs
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8ebf8d806b5decdbc3e694fc62146a55ef53151c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-call-native-dlls-from-managed-code-using-pinvoke"></a>方法: PInvoke を使用してマネージ コードからネイティブ DLL を呼び出す
アンマネージ Dll に実装されている関数は、Platform Invoke (P/invoke) 機能を使用してマネージ コードから呼び出すことができます。 DLL のソース コードが使用できない場合は、相互運用するための唯一のオプションは P/invoke です。 ただし、Visual C は、他の .NET 言語とは異なり、P/invoke する代わりを提供します。 詳細については、次を参照してください。[を使用して C++ Interop (暗黙の PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)です。  
  
## <a name="example"></a>例  
 次のコード例は、Win32 を使用して[問題](http://msdn.microsoft.com/library/windows/desktop/ms724385)ピクセルでの画面の現在の解像度を取得します。  
  
 組み込み型のみを引数として使用し、値を返す関数の場合は、追加の作業は必要ありません。 関数ポインター、配列、および構造体など、他のデータ型では、適切なデータのマーシャ リングすることを確認する追加の属性が必要です。  
  
 必要ありませんは、この例で示したように、グローバル名前空間に存在しないように P/invoke 宣言のある値クラスの静的メンバーを作成するようにします。  
  
```  
// pinvoke_basic.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value class Win32 {  
public:  
   [DllImport("User32.dll")]  
   static int GetSystemMetrics(int);  
  
   enum class SystemMetricIndex {  
      // Same values as those defined in winuser.h.  
      SM_CXSCREEN = 0,  
      SM_CYSCREEN = 1  
   };  
};  
  
int main() {  
   int hRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CXSCREEN) );  
   int vRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CYSCREEN) );  
   Console::WriteLine("screen resolution: {0},{1}", hRes, vRes);  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ での明示的な PInvoke (DllImport 属性) の使用方法](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)