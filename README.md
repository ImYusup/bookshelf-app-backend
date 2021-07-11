# Bookshelf-App-Backend

Actually this repository related same requirement and function with [notes-app-back-end](https://github.com/ImYusup/notes-app-back-end) with adding some challenge featured like as :

**1. All prerequisites have installed properly.**

**2. Create this task with follow body request as shown below :**
```
{
    "name": string,
    "year": number,
    "author": string,
    "summary": string,
    "publisher": string,
    "pageCount": number,
    "readPage": number,
    "reading": boolean
}
```
**- If fail the server shown status code 400 and sample response body as sample shown below :**
    
    ```
    {
        "status": "fail",
        "message": "Gagal menambahkan buku. Mohon isi nama buku"
    }   
    ```

**- If readPage > pageCount the server shown status code 400 and sample response body as sample shown below :**
    
    ```
    {
        "status": "fail",
        "message": "Gagal menambahkan buku. readPage tidak boleh lebih besar dari pageCount"
    }
    ```

**- If fail to create the book, server shown status code 500 and sample response body as sample shown below :**
    
    ```
    {
        "status": "error",
        "message": "Buku gagal ditambahkan"
    }
    ```

**- If success the server shown status code 201 and sample response body as sample shown below :**
    
    ```
    {
        "status": "success",
        "message": "Buku berhasil ditambahkan",
        "data": {
            "bookId": "1L7ZtDUFeGs7VlEt"
        }
    }
    ```

**3. Get shown all books have created before.**

**- The server have returned status code 200 and sample response body as sample shown below :**
    
    ```
    {
        "status": "success",
        "data": {
        "books": [
            {
                "id": "Qbax5Oy7L8WKf74l",
                "name": "Buku A",
                "publisher": "Dicoding Indonesia"
            },
            {
                "id": "1L7ZtDUFeGs7VlEt",
                "name": "Buku B",
                "publisher": "Dicoding Indonesia"
            },
            {
                "id": "K8DZbfI-t3LrY7lD",
                "name": "Buku C",
                "publisher": "Dicoding Indonesia"
            }
         ]
        }
    }
    ```

**- If no book created before, the server shown empty array as sample shown below :**
    
    ```
    {
    "status": "success",
    "data": {
        "books": []
     }
    }
    ```

**4. Get shown details book per id.**
**- If no available id, the server shown status code 404 and sample response body as sample shown below :**
    
    ```
    {
        "status": "fail",
        "message": "Buku tidak ditemukan"
    }
    ```

**- If id is available, the server shown status code 200 and sample response body as sample shown below :**
    
    ```
    {
    "status": "success",
    "data": {
        "book": {
            "id": "aWZBUW3JN_VBE-9I",
            "name": "Buku A Revisi",
            "year": 2011,
            "author": "Jane Doe",
            "summary": "Lorem Dolor sit Amet",
            "publisher": "Dicoding",
            "pageCount": 200,
            "readPage": 26,
            "finished": false,
            "reading": false,
            "insertedAt": "2021-03-05T06:14:28.930Z",
            "updatedAt": "2021-03-05T06:14:30.718Z"
            }
        }   
    }
    ```

**- Get query details book as shown below request. (Optional : adding challenge).**
    
    - ?name (non-case sensitive).
    - ?reading(no reading === 0 and reading === 1).
    - ?finished(not finished === 0 and finished === 1). 

**5. Updated book per id as shown below request.**
```
{
    "name": string,
    "year": number,
    "author": string,
    "summary": string,
    "publisher": string,
    "pageCount": number,
    "readPage": number,
    "reading": boolean
}
```

**- If client can't attach name and request body, the server shown status code 400 and sample response body as sample shown below :**
    
    ```
    {
        "status": "fail",
        "message": "Gagal memperbarui buku. Mohon isi nama buku"
    }
    ```

**- If client attach readPage > pageCount, the server shown status code 400 and sample response body as sample shown below :**
    
    ```
    {
        "status": "fail",
        "message": "Gagal memperbarui buku. readPage tidak boleh lebih besar dari pageCount"
    }
    ```

**- If no available id, the server shown status code 404 and sample response body as sample shown below :**
    
    ```
    {   
        "status": "fail",
        "message": "Gagal memperbarui buku. Id tidak ditemukan"
    }
    ```

**- If updated success the server shown status code 200 and sample response body as sample shown below :**
    
    ```
    {
        "status": "success",
        "message": "Buku berhasil diperbarui"
    }
    ```

**6. Deleted book per id.**

**- If id available but no book created, the server shown status code 404 and sample response body as sample shown below :**
    
    ```
    {
        "status": "fail",
        "message": "Buku gagal dihapus. Id tidak ditemukan"
    }
    ```

**- If id available but have book created, the server shown status code 200 and sample response body as sample shown below :**
    
    ```
    {
        "status": "success",
        "message": "Buku berhasil dihapus"
    }
    ```


### **[Demo here](https://drive.google.com/file/d/1LyYTlZmgi_J94ymjUS-4_msz3GcR4bs8/view?usp=sharing) using screen video recorder automated testing by postman.**