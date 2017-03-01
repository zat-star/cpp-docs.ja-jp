---
title: "関数の構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMemoryState
dev_langs:
- C++
helpviewer_keywords:
- CMemoryState structure
- memory leaks, detecting
- detecting memory leaks
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
caps.latest.revision: 19
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 037c8f075a14346e3428c5e19bfda662c4f3c2b0
ms.lasthandoff: 02/24/2017

---
# <a name="cmemorystate-structure"></a>関数の構造体
プログラムでのメモリ リークを検出するために便利な方法を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
struct CMemoryState  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMemoryState::CMemoryState](#cmemorystate)|メモリのチェックポイントを制御するクラスに似た構造を構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMemoryState::Checkpoint](#checkpoint)|現在のメモリ状態のスナップショット (チェックポイント) を取得します。|  
|[CMemoryState::Difference](#difference)|型の&2; つのオブジェクト間の差を計算`CMemoryState`します。|  
|[CMemoryState::DumpAllObjectsSince](#dumpallobjectssince)|以前のチェックポイント以降には、現在割り当てられているすべてのオブジェクトの概要をダンプします。|  
|[CMemoryState::DumpStatistics](#dumpstatistics)|メモリ割り当ての統計を出力する`CMemoryState`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `CMemoryState`構造体は、基本クラスではありません。  
  
 オブジェクトのメモリには、ヒープに割り当てられたが、必要でなくなったときに割り当てを解除されない場合に、「メモリ リーク」が発生します。 このようなメモリ リークは、メモリ不足のエラーに最終的につながります。 割り当て、プログラム内でメモリを解放するためのいくつかの方法があります。  
  
-   使用して、 `malloc` / **無料**ランタイム ライブラリ関数のファミリです。  
  
-   Windows API のメモリ管理関数を使用して**LocalAlloc**/ **LocalFree**と**GlobalAlloc**/ **GlobalFree**します。  
  
-   C++ を使用して**新しい**と**削除**演算子。  
  
 `CMemoryState`診断だけ簡単にメモリを検出を使用してメモリが割り当てられる場合に発生するリーク、**新しい**演算子を使用して割り当てが解除されない**削除**します。 メモリ管理関数の他の&2; つのグループは、C++ 以外のプログラム、およびこれらとを混在させる**新しい**と**削除**同じプログラム内ではないことをお勧めします。 追加のマクロ`DEBUG_NEW`、置換することは、**新しい**演算子ファイルとメモリの割り当ての行番号を追跡する必要がある場合。 `DEBUG_NEW`通常使用するときに使用される、**新しい**演算子。  
  
 その他の診断と同様、`CMemoryState`診断は、プログラムのデバッグ バージョンで利用可能なだけです。 デバッグ バージョンが必要、 **_DEBUG**定数を定義します。  
  
 使用することができます、プログラムがメモリ リークがあると思われる場合、 `Checkpoint`、**違い**と`DumpStatistics`プログラムの実行中の&2; つのさまざまな時点で、メモリの状態 (割り当てられたオブジェクト) の違いを検出する機能です。 この情報は、関数が割り当てたすべてのオブジェクトがクリーンアップされているかどうかを決定する際に便利です。  
  
 使用することができます割り当てと解放の不均衡が発生した場所を知っているだけも十分な情報を提供しない場合、`DumpAllObjectsSince`前の呼び出し以降に割り当てられたすべてのオブジェクトをダンプ関数を`Checkpoint`します。 このダンプは、割り当て、ソース ファイルと、オブジェクトが割り当てられた行の順序を示します (を使用している場合は、`DEBUG_NEW`の割り当て)、および、オブジェクト、そのアドレス、およびサイズの派生です。 `DumpAllObjectsSince`各オブジェクトを呼び出しても`Dump`関数は、現在の状態に関する情報を提供します。  
  
 使用する方法の詳細についての`CMemoryState`し、その他の診断を参照してください[MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)します。  
  
> [!NOTE]
>  型のオブジェクトの宣言`CMemoryState`してメンバー関数への呼び出しを囲む必要があり、`#if defined(_DEBUG)/#endif`ディレクティブです。 これにより、メモリ診断は、プログラムのデバッグ ビルドにのみ含まれます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CMemoryState`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="a-namecheckpointa--cmemorystatecheckpoint"></a><a name="checkpoint"></a>CMemoryState::Checkpoint  
 スナップショットのメモリの概要を取得し、この格納`CMemoryState`オブジェクトです。  
  
```  
void Checkpoint();
```  
  
### <a name="remarks"></a>コメント  
 `CMemoryState`メンバー関数[違い](#difference)と[DumpAllObjectsSince](#dumpallobjectssince)このスナップショット データを使用します。  
  
### <a name="example"></a>例  
  例を参照してください、[行い](#cmemorystate)コンス トラクターです。  
  
##  <a name="a-namecmemorystatea--cmemorystatecmemorystate"></a><a name="cmemorystate"></a>CMemoryState::CMemoryState  
 空の構築`CMemoryState`が入力する必要がありますオブジェクト、[チェックポイント](#checkpoint)または[違い](#difference)メンバー関数。  
  
```  
CMemoryState();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities&#18;](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]  
  
##  <a name="a-namedifferencea--cmemorystatedifference"></a><a name="difference"></a>CMemoryState::Difference  
 2 つを比較して`CMemoryState`オブジェクトの場合、この違いを格納`CMemoryState`オブジェクトです。  
  
```  
BOOL Difference(
    const CMemoryState& oldState,   
    const CMemoryState& newState);
```  
  
### <a name="parameters"></a>パラメーター  
 *oldState*  
 最初のメモリ状態で定義されている、`CMemoryState`チェックポイントです。  
  
 *newState*  
 定義されている新しいメモリ状態、`CMemoryState`チェックポイントです。  
  
### <a name="return-value"></a>戻り値  
 2 つのメモリ状態が異なっている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 [チェックポイント](#checkpoint)の&2; つのメモリ状態パラメーターごとに呼び出す必要があります。  
  
### <a name="example"></a>例  
  例を参照してください、[行い](#cmemorystate)コンス トラクターです。  
  
##  <a name="a-namedumpallobjectssincea--cmemorystatedumpallobjectssince"></a><a name="dumpallobjectssince"></a>CMemoryState::DumpAllObjectsSince  
 呼び出し、`Dump`クラスから派生した型のすべてのオブジェクトの関数`CObject`を割り当てられた (とまだ割り当てられている)、前回の[チェックポイント](#checkpoint)この呼び出す`CMemoryState`オブジェクトです。  
  
```  
void DumpAllObjectsSince() const;

 
```  
  
### <a name="remarks"></a>コメント  
 呼び出す`DumpAllObjectsSince`初期化されていないと`CMemoryState`オブジェクトが現在メモリ内のすべてのオブジェクトをダンプします。  
  
### <a name="example"></a>例  
  例を参照してください、[行い](#cmemorystate)コンス トラクターです。  
  
##  <a name="a-namedumpstatisticsa--cmemorystatedumpstatistics"></a><a name="dumpstatistics"></a>CMemoryState::DumpStatistics  
 簡潔なメモリ統計情報レポートを印刷、`CMemoryState`を果たすオブジェクト、[違い](#difference)メンバー関数。  
  
```  
void DumpStatistics() const;

 
```  
  
### <a name="remarks"></a>コメント  
 レポートに印刷されますが、 [afxDump](http://msdn.microsoft.com/library/4b3cfa3f-fb75-456a-9d99-a5601acbcb11)デバイス、次に示します。  
  
 レポートの例では、数 (または容量) の情報を提供します。  
  
-   空きブロック数  
  
-   normal ブロック  
  
-   CRT ブロック  
  
-   ignore ブロック  
  
-   クライアント ブロック  
  
-   バイト単位で同時に、プログラムによって使用された最大メモリ  
  
-   合計メモリ (バイト) をプログラムによって現在使用  
  
 空きブロックの解放が遅れている場合はブロックの数は`afxMemDF`に設定されている**delayFreeMemDF**します。 詳細については、次を参照してください。 [afxMemDF](diagnostic-services.md#afxmemdf)、"MFC マクロとグローバル」に記載します。 参照してください[デバッグ ヒープ上のブロックの型](http://msdn.microsoft.com/en-us/db2e7f62-0679-4b39-a23f-26f2c2f407c5)の詳細については、これらの種類をブロックするのです。  
  
### <a name="example"></a>例  
  次のコードに配置する必要があります*projname*App.cpp します。 次のグローバル変数を定義します。  
  
 [!code-cpp[NVC_MFC_Utilities #&40;](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]  
  
 `InitInstance`関数の行を追加します。  
  
 [!code-cpp[NVC_MFC_Utilities #&41;](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]  
  
 ハンドラーを追加、`ExitInstance`機能し、次のコードを使用します。  
  
 [!code-cpp[NVC_MFC_Utilities #&42;](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]  
  
 ここでの出力を表示するデバッグ モードでプログラムを実行することができます、`DumpStatistics`関数です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)




