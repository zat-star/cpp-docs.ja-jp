---
title: "方法: PInvoke を使用してマネージ コードからネイティブ DLL を呼び出す | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "データ マーシャリング [C++], 呼び出し (ネイティブ DLL を)"
  - "相互運用 [C++], 呼び出し (ネイティブ DLL を)"
  - "マーシャリング [C++], 呼び出し (ネイティブ DLL を)"
  - "プラットフォーム呼び出し [C++], 呼び出し (ネイティブ DLL を)"
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# 方法: PInvoke を使用してマネージ コードからネイティブ DLL を呼び出す
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プラットフォーム呼び出し \(P\/Invoke\) 機能を使用して、マネージ コードからアンマネージ DLL で実装される関数を呼び出すことができます。  DLL のソース コードが利用できない場合、相互運用できるようにするには P\/Invoke を使用する以外方法はありません。  ただし、他の .NET 言語とは異なり、Visual C\+\+ には P\/Invoke 以外の方法が用意されています。  詳細については、「[C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)」を参照してください。  
  
## 使用例  
 次のコード例は、Win32 [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) 関数を使用して、現在の画面の解像度をピクセル単位で取得します。  
  
 引数として組み込みの型のみを使用して値を返す関数の場合、特別な作業を行う必要ありません。  関数ポインター、配列、構造体など、その他のデータ型の場合、適切なデータ マーシャリングを確実に行うために追加の属性が必要です。  
  
 この例で示すように、P\/Invoke 宣言がグローバル名前空間に存在することがないように、P\/Invoke 宣言を値クラスの静的メンバーにすることをお勧めします。  
  
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
  
## 参照  
 [C\+\+ での明示的な PInvoke \(DllImport 属性\) の使用方法 ](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)