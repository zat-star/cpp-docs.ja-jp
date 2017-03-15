---
title: "方法: PInvoke を使用して構造体をマーシャリングする | Microsoft Docs"
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
  - "データ マーシャリング [C++], 構造体"
  - "相互運用 [C++], 構造体"
  - "マーシャリング [C++], 構造体"
  - "プラットフォーム呼び出し [C++], 構造体"
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# 方法: PInvoke を使用して構造体をマーシャリングする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このドキュメントでは、P\/Invoke を使用して <xref:System.String> のインスタンスを提供するマネージ関数から、C スタイルの文字列を受け入れるネイティブ関数を呼び出す方法を説明します。  P\/Invoke はほとんどコンパイル時のエラーを報告せず、タイプ セーフでなく、実装に時間がかかることがあるため、P\/Invoke の代わりに C\+\+ Interop を使用することが推奨されていますが、アンマネージ API が DLL としてパッケージされてソース コードとして使用できない場合は、P\/Invoke を使用する以外に方法はありません。  P\/Invoke を使用しない場合は、次のドキュメントを参照してください。  
  
-   [C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [How to: Marshal Structures Using PInvoke](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
 ネイティブ構造体とマネージ構造体は、既定では、メモリ上で別々にレイアウトされているため、マネージ境界またはアンマネージ境界を超えて構造体を正しく渡すには、データの整合性を維持するための特別な手順が必要です。  
  
 このドキュメントは、ネイティブ構造体と等価なマネージ構造体を定義するために必要な手順、およびその結果の構造体をアンマネージ関数に渡す方法について説明します。  このドキュメントでは、文字列またはポインターを含まない単純な構造体を使用することを前提とします。  blittable でない相互運用性については、「[C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)」を参照してください。  P\/Invoke は、戻り値として blittable でない値を指定できません。  blittable 型の場合、マネージ コードとアンマネージ コードでの表現は同じになります。  詳細については、「[Blittable 型と非 Blittable 型](../Topic/Blittable%20and%20Non-Blittable%20Types.md)」を参照してください。  
  
 マネージ境界またはアンマネージ境界を超えて単純な blittable 構造体をマーシャリングするには、まず、各ネイティブ構造体のマネージ バージョンを定義する必要があります。  データ レイアウト以外のネイティブ バージョンとマネージ バージョンの 2 つの構造体の間に関係は存在しないので、これらの構造体には任意の有効な名前を指定できます。  したがって、マネージ バージョンには、ネイティブ バージョンと同じサイズのフィールドを同じ順序で含めることが重要です \(マネージ バージョンとネイティブ バージョンの構造体が等価であることを確認する機構はありません。したがって、互換性が維持されていない場合も、実行時までわかりません。  プログラマは、確実に 2 つの構造体に同じデータ レイアウトを構築する必要があります\)。  
  
 パフォーマンスの向上のために、マネージ構造体のメンバーを再配置する場合があるため、<xref:System.Runtime.InteropServices.StructLayoutAttribute> 属性を使用して、構造体が連続して配置されていることを示す必要があります。  構造体のパッキング設定をネイティブ構造体が使用するのと同じものに明示的に設定するのも賢明な方法です \(ただし既定では、Visual C\+\+ は両方のマネージ コードに対して 8 バイトの構造体のパッキングを使用します\)。  
  
1.  次に、構造体を受け入れるアンマネージ関数に対応するエントリ ポイントを宣言するには、<xref:System.Runtime.InteropServices.DllImportAttribute> を使用します。ただし、関数シグネチャ内ではマネージ バージョンの構造体を使用します。これは、この 2 つのバージョンの構造体に同じ名前を使用する場合は問題になります。  
  
2.  これで、マネージ コードは、マネージ バージョンの構造体を、実際にマネージ関数であるかのようにアンマネージ関数に渡すことができるようになりました。  次の例のように、値または参照のいずれかを使用してこれらの構造体を渡すことができます。  
  
## 使用例  
 次のコードは、アンマネージ モジュールとマネージ モジュールで構成されます。  アンマネージ モジュールは、Location と呼ばれる構造体と、Location 構造体の 2 つのインスタンスを受け入れる GetDistance と呼ばれる関数を定義する DLL です。  2 つ目のモジュールは、GetDistance 関数をインポートするマネージ コマンド ライン アプリケーションですが、Location 構造体と等価のマネージ構造体である MLocation について GetDistance 関数を定義します。  実際には、2 つのバージョンの構造体に同じ名前を使用する場合がありますが、マネージ バージョンについて DllImport プロトタイプが定義されていることを示すため、ここでは両者に別々の名前を使用します。  
  
 \/clr を指定してマネージ モジュールをコンパイルします。\/clr:pure を使用してもかまいません。  
  
 ただし、DLL のどの部分も、従来の \#include ディレクティブを使用してのマネージ コードへの公開はしていません。  実際には、DLL には実行時にしかアクセスしないため、DllImport を使ってインポートされた関数についての問題は、コンパイル時には検出されません。  
  
```  
// TraditionalDll3.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
#include <stdio.h>  
#include <math.h>  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
   #define TRADITIONALDLL_API __declspec(dllexport)  
#else  
   #define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
#pragma pack(push, 8)  
struct Location {  
   int x;  
   int y;  
};  
#pragma pack(pop)  
  
extern "C" {  
   TRADITIONALDLL_API double GetDistance(Location, Location);  
   TRADITIONALDLL_API void InitLocation(Location*);  
}  
  
double GetDistance(Location loc1, Location loc2) {  
   printf_s("[unmanaged] loc1(%d,%d)", loc1.x, loc1.y);  
   printf_s(" loc2(%d,%d)\n", loc2.x, loc2.y);  
  
   double h = loc1.x - loc2.x;  
   double v = loc1.y = loc2.y;  
   double dist = sqrt( pow(h,2) + pow(v,2) );  
  
   return dist;  
}  
  
void InitLocation(Location* lp) {  
   printf_s("[unmanaged] Initializing location...\n");  
   lp->x = 50;  
   lp->y = 50;  
}  
```  
  
## 使用例  
  
```  
// MarshalStruct_pi.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Sequential, Pack=8)]  
value struct MLocation {  
   int x;  
   int y;  
};  
  
value struct TraditionalDLL {  
   [DllImport("TraditionalDLL3.dll")]  
   static public double GetDistance(MLocation, MLocation);  
   [DllImport("TraditionalDLL3.dll")]  
   static public double InitLocation(MLocation*);  
};  
  
int main() {  
   MLocation loc1;  
   loc1.x = 0;  
   loc1.y = 0;  
  
   MLocation loc2;  
   loc2.x = 100;  
   loc2.y = 100;  
  
   double dist = TraditionalDLL::GetDistance(loc1, loc2);  
   Console::WriteLine("[managed] distance = {0}", dist);  
  
   MLocation loc3;  
   TraditionalDLL::InitLocation(&loc3);  
   Console::WriteLine("[managed] x={0} y={1}", loc3.x, loc3.y);  
}  
```  
  
  **\[unmanaged\] loc1\(0,0\) loc2\(100,100\)**  
**\[managed\] distance \= 141.42135623731**  
**\[unmanaged\] Initializing location...**  
**\[managed\] x\=50 y\=50**   
## 参照  
 [C\+\+ での明示的な PInvoke \(DllImport 属性\) の使用方法 ](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)