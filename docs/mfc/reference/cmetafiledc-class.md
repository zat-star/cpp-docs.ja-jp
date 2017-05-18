---
title: "CMetaFileDC クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMetaFileDC
- AFXEXT/CMetaFileDC
- AFXEXT/CMetaFileDC::CMetaFileDC
- AFXEXT/CMetaFileDC::Close
- AFXEXT/CMetaFileDC::CloseEnhanced
- AFXEXT/CMetaFileDC::Create
- AFXEXT/CMetaFileDC::CreateEnhanced
dev_langs:
- C++
helpviewer_keywords:
- CMetaFileDC class
- Windows metafiles [C++]
- metafiles, implementing
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
caps.latest.revision: 23
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 4bff4d7601c4ffbc6fe5cbe73f5e057b79abf1e5
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmetafiledc-class"></a>CMetaFileDC クラス
イメージやテキストを自由に作成するための一連のグラフィック デバイス インターフェイス (GDI) コマンドを含む Windows のメタファイルを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMetaFileDC : public CDC  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMetaFileDC::CMetaFileDC](#cmetafiledc)|`CMetaFileDC` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMetaFileDC::Close](#close)|デバイス コンテキストを閉じ、メタファイル ハンドルを作成します。|  
|[CMetaFileDC::CloseEnhanced](#closeenhanced)|拡張メタファイル デバイス コンテキストを終了し、拡張メタファイル ハンドルを作成します。|  
|[CMetaFileDC::Create](#create)|Windows のメタファイル デバイス コンテキストを作成し、それにアタッチ、`CMetaFileDC`オブジェクトです。|  
|[CMetaFileDC::CreateEnhanced](#createenhanced)|拡張形式メタファイルのメタファイル デバイス コンテキストを作成します。|  
  
## <a name="remarks"></a>コメント  
 Windows のメタファイルを実装するには、最初に作成、`CMetaFileDC`オブジェクトです。 呼び出す、`CMetaFileDC`コンス トラクター、まず、[作成](#create)メンバー関数は、Windows のメタファイル デバイス コンテキストを作成し、それにアタッチ、`CMetaFileDC`オブジェクトです。  
  
 次に、送信、`CMetaFileDC`オブジェクトのシーケンス`CDC`を再生するための対象となる GDI コマンドです。 出力を作成し GDI コマンドのみ`MoveTo`と`LineTo`、使用することができます。  
  
 メタファイルに必要なコマンドを送信した後、**閉じる**がメタファイル デバイス コンテキストを閉じ、メタファイル ハンドルを返すメンバー関数。 破棄、`CMetaFileDC`オブジェクトです。  
  
 [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile)メタファイルを繰り返し再生するメタファイルのハンドルを使用し、ことができます。 メタファイルもによって操作できる Windows 関数など、 [CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480)メタファイルをディスクにコピーします。  
  
 メタファイルを不要になったときにメモリから削除、 [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) Windows の機能です。  
  
 実装することも、`CMetaFileDC`オブジェクトを処理できるようにの両方の呼び出しの出力し、GDI の呼び出しをなど属性`GetTextExtent`します。 このようなメタファイルはより柔軟しより簡単に再利用できます全般 GDI コードでは、多くの場合、さまざまな出力と属性の呼び出しで構成されます。 `CMetaFileDC`クラスは&2; つのデバイス コンテキストを継承`m_hDC`と`m_hAttribDC`から`CDC`します。 `m_hDC`デバイス コンテキストでは、すべてを処理[CDC](../../mfc/reference/cdc-class.md) GDI の呼び出しを出力して、`m_hAttribDC`デバイス コンテキストでは、すべてを処理`CDC`GDI 属性では。 通常、これらの&2; つのデバイス コンテキストでは、同じデバイスを参照してください。 場合に`CMetaFileDC`、DC の属性に設定されて**NULL**既定です。  
  
 画面、プリンター、または、メタファイル以外のデバイスをポイントしを呼び出す&2; つ目のデバイス コンテキストを作成、`SetAttribDC`メンバー関数を使用して新しいデバイス コンテキストを結び付けるため`m_hAttribDC`です。 詳細については、GDI の呼び出しは、新規作成 をリダイレクトよう`m_hAttribDC`します。 出力 GDI 呼び出しを使用する代替`m_hDC`メタファイルを表します。  
  
 詳細については`CMetaFileDC`を参照してください[デバイス コンテキスト](../../mfc/device-contexts.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CMetaFileDC`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="close"></a>CMetaFileDC::Close  
 メタファイル デバイス コンテキストを閉じを使用してメタファイルを再生するために使用する Windows のメタファイル ハンドルを作成、 [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile)メンバー関数。  
  
```  
HMETAFILE Close();
```  
  
### <a name="return-value"></a>戻り値  
 有効な**終了した**関数が成功した場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 Windows のメタファイル ハンドルこともできますなどの Windows の関数でのメタファイルを操作する[CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480)します。  
  
 使用後に、Windows を呼び出すことにより、メタファイルを削除[DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537)関数です。  
  
##  <a name="closeenhanced"></a>CMetaFileDC::CloseEnhanced  
 拡張メタファイル デバイス コンテキストを終了し、拡張形式メタファイルを識別するハンドルを返します。  
  
```  
HENHMETAFILE CloseEnhanced();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、拡張メタファイルのハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションは、この関数によって返される拡張メタファイルのハンドルを使用して、次のタスクを実行できます。  
  
-   拡張メタファイルに格納されている画像を表示します。  
  
-   拡張メタファイルのコピーを作成します。  
  
-   列挙、編集、または拡張メタファイル内の個々 のレコードのコピー  
  
-   拡張メタファイルのヘッダーからメタファイルの内容の説明 (オプション) を取得します。  
  
-   拡張メタファイルのヘッダーのコピーを取得します。  
  
-   拡張メタファイルのバイナリのコピーを取得します。  
  
-   オプションのパレットで色を列挙します。  
  
-   拡張形式メタファイルを Windows 形式メタファイルに変換します。  
  
 Win32 を呼び出すことによって、ハンドルを解除する必要があるアプリケーションで拡張メタファイルのハンドルが不要になった場合は、 **DeleteEnhMetaFile**関数です。  
  
##  <a name="cmetafiledc"></a>CMetaFileDC::CMetaFileDC  
 構築、 `CMetaFileDC`&2; つのステップ内のオブジェクト。  
  
```  
CMetaFileDC();
```  
  
### <a name="remarks"></a>コメント  
 最初に、呼び出す`CMetaFileDC`、物書き**作成**、Windows のメタファイル デバイス コンテキストを作成およびそれにアタッチする、`CMetaFileDC`オブジェクトです。  
  
##  <a name="create"></a>CMetaFileDC::Create  
 構築、 `CMetaFileDC`&2; つのステップ内のオブジェクト。  
  
```  
BOOL Create(LPCTSTR lpszFilename = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *場合*  
 Null で終わる文字列へのポインター。 作成するメタファイルのファイル名を指定します。 場合*場合*は**NULL**、新しいメモリ内のメタファイルを作成します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 最初に、コンス トラクターを呼び出す`CMetaFileDC`、物書き**作成**、Windows のメタファイル デバイス コンテキストを作成およびそれにアタッチする、`CMetaFileDC`オブジェクトです。  
  
##  <a name="createenhanced"></a>CMetaFileDC::CreateEnhanced  
 拡張形式メタファイルのデバイス コンテキストを作成します。  
  
```  
BOOL CreateEnhanced(
    CDC* pDCRef,  
    LPCTSTR lpszFileName,  
    LPCRECT lpBounds,  
    LPCTSTR lpszDescription);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDCRef`  
 拡張メタファイルの参照のデバイスを識別します。  
  
 `lpszFileName`  
 Null で終わる文字列へのポインター。 作成する拡張メタファイルのファイル名を指定します。 このパラメーターがある場合**NULL**、拡張メタファイル メモリ ベースとその内容をオブジェクトが破棄されるとき、または失われるは、Win32 **DeleteEnhMetaFile**関数が呼び出されます。  
  
 `lpBounds`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)データ構造体、または[CRect](../../atl-mfc-shared/reference/crect-class.md)内のディメンションを指定するオブジェクト**HIMETRIC**拡張メタファイルに格納されている画像の (.01 ミリメートル単位) の単位です。  
  
 `lpszDescription`  
 画像と画像のタイトルを作成したアプリケーションの名前を指定する&0; で終わる文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、拡張メタファイルのデバイス コンテキストのハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 このドメイン コント ローラーは、デバイスに依存しない画像を格納できます。  
  
 Windows で識別される参照デバイスを使用して、`pDCRef`解像度や、デバイスを画像表示されていた元の単位を記録するパラメーターです。 場合、`pDCRef`パラメーターは**NULL**、基準として現在のディスプレイ デバイスを使用します。  
  
 左と上のメンバー、`RECT`がデータ構造が指す、`lpBounds`パラメーターより小さくなければなりません右側と下部にあるメンバーをそれぞれします。 図では、四角形の端点が含まれています。 場合`lpBounds`は**NULL**、グラフィック デバイス インターフェイス (GDI) は、アプリケーションによって描画される画像を囲む最小の四角形の寸法を計算します。 `lpBounds`可能であれば、パラメーターを指定する必要があります。  
  
 指す文字列、`lpszDescription`パラメーターはアプリケーションの名前と画像の名前の間での null 文字を含める必要があり、2 つの null 文字で終了する必要があります: たとえば、"XYZ グラフィックス Editor\0Bald Eagle\0\0、"\0 が null 文字を表します。 場合`lpszDescription`は**NULL**、拡張メタファイルのヘッダーに対応するエントリはありません。  
  
 アプリケーションでは、この関数によって作成されたドメイン コント ローラーを使用して拡張メタファイルにグラフィック画像を保存します。 このドメイン コント ローラーを識別するハンドルは、任意の GDI 関数に渡すことができます。  
  
 アプリケーションは、拡張メタファイルに画像を保存した後、画像を表示できる任意の出力デバイスに呼び出すことによって、`CDC::PlayMetaFile`関数です。 Windows が指す長方形を使用して、画像を表示するときに、`lpBounds`パラメーターと位置し、スケール、図を参照するデバイスからの解像度のデータです。 この関数によって返されるデバイス コンテキストには、任意の新しい DC に関連付けられている同じ既定の属性が含まれています。  
  
 アプリケーションは、Win32 を使用する必要があります**GetWinMetaFileBits**拡張メタファイルを以前の Windows のメタファイル形式に変換する関数。  
  
 拡張メタファイルのファイル名を使用する必要があります、します。EMF 拡張子です。  
  
## <a name="see-also"></a>関連項目  
 [CDC クラス](../../mfc/reference/cdc-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




