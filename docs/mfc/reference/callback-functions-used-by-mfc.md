---
title: "MFC で使用するコールバック関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.functions
dev_langs:
- C++
helpviewer_keywords:
- callback functions, MFC
- MFC, callback functions
- functions [C++], callback
- callback functions
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: d4b97ed874b145f9c6d9a9536476243bba0fd1c1
ms.openlocfilehash: 08c6f547c95adb4c6794ec71259888d390e42e92
ms.contentlocale: ja-jp
ms.lasthandoff: 03/06/2017

---
# <a name="callback-functions-used-by-mfc"></a>MFC で使われているコールバック関数
次の&3; つのコールバック関数は、Microsoft Foundation Class ライブラリに表示されます。 これらのコールバック関数に渡す[cdc::enumobjects](../../mfc/reference/cdc-class.md#enumobjects)、 [cdc::graystring](../../mfc/reference/cdc-class.md#graystring)、および[cdc::setabortproc](../../mfc/reference/cdc-class.md#setabortproc)します。 すべてのコールバック関数がコールバックの境界を越えて例外がスローされることはできませんので、Windows に復帰する前に MFC の例外をトラップする必要があることに注意してください。 例外の詳細については、記事を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)します。  

|名前||  
|----------|-----------------|  
|[CDC::EnumObjects 用コールバック関数](#enum_objects)||  
|[CDC::GrayString 用コールバック関数](#graystring)||
|[CDC::SetAbortProc 用コールバック関数](#setabortproc)|| 

## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h 

## <a name="enum_objects"></a>Cdc::enumobjects 用コールバック関数
*ObjectFunc*名は、アプリケーションによって提供される関数名のプレース ホルダーです。  
  
### <a name="syntax"></a>構文  
  
```  
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,  
    LPSTR* lpData);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszLogObject*  
 指す、 [LOGPEN](../../mfc/reference/logpen-structure.md)または[LOGBRUSH](../../mfc/reference/logbrush-structure.md)オブジェクトの論理属性に関する情報を格納するデータ構造です。  
  
 `lpData`  
 アプリケーションによって提供されるデータへのポインターが渡される、`EnumObjects`関数です。  
  
### <a name="return-value"></a>戻り値  
 コールバック関数の結果、`int`です。 この戻り値の値は、ユーザー定義です。 コールバック関数は 0 を返した場合`EnumObjects`早期の列挙を停止します。  
  
### <a name="remarks"></a>コメント  
 実際の名前をエクスポートする必要があります。  
  
## <a name="graystring"></a>Cdc::graystring 用コールバック関数
*OutputFunc*アプリケーションによって提供されるコールバック関数名のプレース ホルダーです。  
  
### <a name="syntax"></a>構文  
  
```  
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,  
    LPARAM lpData,  
    int nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `hDC`  
 少なくともビットマップ メモリ デバイス コンテキストを識別する幅と高さで指定された`nWidth`と`nHeight`に`GrayString`します。  
  
 `lpData`  
 描画される文字列を指します。  
  
 `nCount`  
 出力する文字数を指定します。  
  
### <a name="return-value"></a>戻り値  
 コールバック関数の戻り値である必要があります**TRUE**成功した場合は以外の場合は**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 コールバック関数 (*OutputFunc*) 座標 (0,&0;) を基準としたイメージを描画する必要がなく (*x*、 *y*)。  

## <a name="setabortproc"></a>Cdc::setabortproc 用コールバック関数
名前*AbortFunc*はアプリケーションによって提供される関数名のプレース ホルダーです。  
  
### <a name="syntax"></a>構文  
  
```  
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,  
    int code);
```  
  
### <a name="parameters"></a>パラメーター  
 *hPr*  
 デバイス コンテキストを識別します。  
  
 `code`  
 エラーが発生したかどうかを指定します。 エラーが発生していない場合は 0 になります。 **させることでより**プリント マネージャーがディスク領域が不足が現在、多くのディスク領域は、アプリケーションが待機する場合は、使用可能になる場合。 場合`code`は**させることでより**アプリケーションは、印刷ジョブを中断する必要はありません。 そうでない場合に呼び出すことによって、印刷マネージャーを生成する必要があります、 **PeekMessage**または**GetMessage** Windows の機能です。  
  
### <a name="return-value"></a>戻り値  
 中止ハンドラー関数の戻り値は、印刷ジョブは、続行する場合は 0 以外および 0 が取り消された場合です。  
  
### <a name="remarks"></a>コメント  
 」の「解説」セクションの説明に従って実際名前をエクスポートする必要があります[cdc::setabortproc](../../mfc/reference/cdc-class.md#setabortproc)します。  
 
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](structures-styles-callbacks-and-message-maps.md)
 [cdc::enumobjects](../../mfc/reference/cdc-class.md#enumobjects)
 [cdc::setabortproc](../../mfc/reference/cdc-class.md#setabortproc)
 [cdc::graystring](../../mfc/reference/cdc-class.md#graystring)


