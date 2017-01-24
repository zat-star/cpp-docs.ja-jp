---
title: "方法: ADO.NET の SAFEARRAY をマーシャリングする (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ADO.NET [C++], マーシャリング (SAFEARRAY 型を)"
  - "SAFEARRAY, マーシャリング"
ms.assetid: 1034b9d7-ecf1-40f7-a9ee-53180e87a58c
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: ADO.NET の SAFEARRAY をマーシャリングする (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

データベースにネイティブな `SAFEARRAY` を追加する方法、およびデータベースのマネージ配列をネイティブな `SAFEARRAY` にマーシャリングする方法について説明します。  
  
## 使用例  
 この例では、ADO.NET <xref:System.Data.DataTable> オブジェクトとやり取りするための DatabaseClass というクラスが作成されます。  このクラスはネイティブな C\+\+ `class` です \(`ref class` や `value class` とは異なります\)。  これは、ネイティブ コードからこのクラスを使用するために必要なもので、マネージ型をネイティブ コードで使用することはできません。  このクラスは、クラスの宣言の前に `#pragma managed` ディレクティブが付いていることからわかるように、CLR を対象としてコンパイルされます。  このディレクティブの詳細については、「[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)」を参照してください。  
  
 DatabaseClass クラスのプライベート メンバーは `gcroot<DataTable ^> table` です。  ネイティブ型にはマネージ型は含まれないため、`gcroot` キーワードが必要です。  `gcroot` の詳細については、「[方法: ネイティブ型のハンドルを宣言する](../dotnet/how-to-declare-handles-in-native-types.md)」を参照してください。  
  
 この例のコードの他の部分は、`#pragma unmanaged` ディレクティブが `main` の前についていることからわかるように、ネイティブな C\+\+ コードです。  この例では、DatabaseClass の新しいインスタンスを作成し、そのメソッドを呼び出し、テーブルを作成してテーブルのいくつかの行を設定します。  ネイティブな `SAFEARRAY` 型は、データベース列 ArrayIntsCol の値として渡されます。  DatabaseClass 内では、<xref:System.Runtime.InteropServices?displayProperty=fullName> 名前空間にあるマーシャリング機能を使用して、これらの `SAFEARRAY` 型がマネージ オブジェクトにマーシャリングされます。  特に、<xref:System.Runtime.InteropServices.Marshal.Copy%2A> メソッドは `SAFEARRAY` を整数のマネージ配列にマーシャリングするときに、また <xref:System.Runtime.InteropServices.Marshal.Copy%2A> メソッドは整数のマネージ配列を `SAFEARRAY` にマーシャリングするときに使用されます。  
  
```  
// adonet_marshal_safearray.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(SAFEARRAY *arrayIntsColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        int len = arrayIntsColValue->rgsabound[0].cElements;  
        array<int> ^arr = gcnew array<int>(len);  
  
        int *pData;  
        SafeArrayAccessData(arrayIntsColValue, (void **)&pData);  
        Marshal::Copy(IntPtr(pData), arr, 0, len);  
        SafeArrayUnaccessData(arrayIntsColValue);  
  
        row["ArrayIntsCol"] = arr;  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("ArrayIntsCol",  
            Type::GetType("System.Int32[]"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, SAFEARRAY **values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringUni(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed array  
            // of Int32s to a SAFEARRAY of type VT_I4.  
            values[i] = SafeArrayCreateVector(VT_I4, 0, 10);  
            int *pData;  
            SafeArrayAccessData(values[i], (void **)&pData);  
            Marshal::Copy((array<int> ^)rows[i][columnStr], 0,  
                IntPtr(pData), 10);  
            SafeArrayUnaccessData(values[i]);  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
  
    // Create a standard array.  
    int originalArray[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
  
    // Create a SAFEARRAY.  
    SAFEARRAY *psa;  
    psa = SafeArrayCreateVector(VT_I4, 0, 10);  
  
    // Copy the data from the original array to the SAFEARRAY.  
    int *pData;  
    HRESULT hr = SafeArrayAccessData(psa, (void **)&pData);  
    memcpy(pData, &originalArray, 40);  
    SafeArrayUnaccessData(psa);  
    db->AddRow(psa);  
  
    // Now retrieve the rows and display their contents.  
    SAFEARRAY *values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"ArrayIntsCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        int *pData;  
        SafeArrayAccessData(values[i], (void **)&pData);  
        for (int j = 0; j < 10; j++)  
        {  
            cout << pData[j] << " ";  
        }  
        cout << endl;  
        SafeArrayUnaccessData(values[i]);  
  
        // Deallocate the memory allocated using  
        // SafeArrayCreateVector.  
        SafeArrayDestroy(values[i]);  
    }  
  
    SafeArrayDestroy(psa);  
    delete db;  
  
    return 0;  
}  
```  
  
  **0 1 2 3 4 5 6 7 8 9**   
## コードのコンパイル  
  
-   コマンド ラインからコードをコンパイルするには、コード例を adonet\_marshal\_safearray.cpp というファイルに保存し、次のステートメントを入力します。  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp  
    ```  
  
## .NET Framework セキュリティ  
 ADO.NET に関するセキュリティの詳細については、「[ADO.NET アプリケーションのセキュリティ保護](../Topic/Securing%20ADO.NET%20Applications.md)」を参照してください。  
  
## 参照  
 <xref:System.Runtime.InteropServices>   
 [データ アクセス](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](../Topic/ADO.NET.md)   
 [Interoperability](http://msdn.microsoft.com/ja-jp/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [ネイティブと .NET の相互運用性](../Topic/Native%20and%20.NET%20Interoperability.md)