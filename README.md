https://www.twilio.com/blog/drop-in-audio-chat-django-react-twilio-programmable-voice
did python -m venv env instead of python3

for the gitignore
https://djangowaves.com/tips-tricks/gitignore-for-a-django-project/


don't rename folder after creating venv

this did not work in powershell
curl -X POST https://2eec-2600-1010-b046-ad33-c051-6ad9-bbe4-5533.ngrok.io/api/rooms -d "roomName=jokes" -d "participantName=user_one"
says Cannot bind parameter because parameter 'd' is specified 
more than once. To provide multiple values to parameters that can accept         
multiple values, use the array syntax. For example, "-parameter 
value1,value2,value3".

this did not work, says Invoke-WebRequest : A parameter cannot be found that matches parameter name 'X'.
At line:1 char:6
curl -X POST https://2eec-2600-1010-b046-ad33-c051-6ad9-bbe4-5533.ngrok.io/api/rooms -d "roomName=jokes&participantName=user_one"

curl works in command line but not on powershell for some reason
curl https://swapi.dev/api/people/1

this somewhat worked in command prompt, but it's not the correct response. it returns this whole html thing. on the ngrok terminal, it says 500 internal server error. 
curl -X POST https://2eec-2600-1010-b046-ad33-c051-6ad9-bbe4-5533.ngrok.io/api/rooms -d "roomName=jokes" -d "participantLabel=user_one"
on the django terminal it says 
Internal Server Error: /api/rooms
Traceback (most recent call last):
  File "C:\Users\User\anaconda3\lib\site-packages\django\utils\datastructures.py", line 77, in __getitem__
    list_ = super().__getitem__(key)
KeyError: 'participantLabel'

During handling of the above exception, another exception occurred:
Traceback (most recent call last):
  File "C:\Users\User\anaconda3\lib\site-packages\django\core\handlers\exception.py", line 34, in inner
    response = get_response(request)
  File "C:\Users\User\anaconda3\lib\site-packages\django\core\handlers\base.py", line 126, in _get_response
    response = self.process_exception_by_middleware(e, request)    
  File "C:\Users\User\anaconda3\lib\site-packages\django\core\handlers\base.py", line 124, in _get_response
    response = wrapped_callback(request, *callback_args, **callback_kwargs)
  File "C:\Users\User\anaconda3\lib\site-packages\django\views\generic\base.py", line 68, in view
    return self.dispatch(request, *args, **kwargs)
  File "C:\Users\User\anaconda3\lib\site-packages\django\utils\decorators.py", line 45, in _wrapper
    return bound_method(*args, **kwargs)
  File "C:\Users\User\anaconda3\lib\site-packages\django\views\decorators\csrf.py", line 54, in wrapped_view
    return view_func(*args, **kwargs)
  File "C:\Users\User\anaconda3\lib\site-packages\django\views\generic\base.py", line 88, in dispatch
    return handler(request, *args, **kwargs)
  File "C:\swe\twilio-django-react\api\views.py", line 12, in post 
    participant_label = request.POST["participantLabel"]
  File "C:\Users\User\anaconda3\lib\site-packages\django\utils\datastructures.py", line 79, in __getitem__
    raise MultiValueDictKeyError(key)
django.utils.datastructures.MultiValueDictKeyError: 'participantLabel'
[06/Mar/2022 16:37:17] "POST /api/rooms HTTP/1.1" 500 97659

the tutorial might have inconsistently used participantLabel and participantName because theyre stupid, so try 
curl -X POST https://2eec-2600-1010-b046-ad33-c051-6ad9-bbe4-5533.ngrok.io/api/rooms -d "roomName=jokes" -d "participantLabel=user_one"
and it is working


had to signup with ngrok, copy authtoken on their site, then do 
ngrok authtoken <authtoken>




using the twilio first key



curl -X GET https://2eec-2600-1010-b046-ad33-c051-6ad9-bbe4-5533.ngrok.io/api/token/alex
now im getting the long html error response again, in terminal of django it says 
Internal Server Error: /api/token/alex
Traceback (most recent call last):
  File "C:\Users\User\anaconda3\lib\site-packages\django\core\handlers\exception.py", line 34, in inner
    response = get_response(request)
  File "C:\Users\User\anaconda3\lib\site-packages\django\core\handlers\base.py", line 126, in _get_response
    response = self.process_exception_by_middleware(e, request)
  File "C:\Users\User\anaconda3\lib\site-packages\django\core\handlers\base.py", line 124, in _get_response
    response = wrapped_callback(request, *callback_args, **callback_kwargs)  File "C:\Users\User\anaconda3\lib\site-packages\django\views\generic\base.py", line 68, in view
    return self.dispatch(request, *args, **kwargs)
  File "C:\Users\User\anaconda3\lib\site-packages\django\views\generic\base.py", line 88, in dispatch
    return handler(request, *args, **kwargs)
  File "C:\swe\twilio-django-react\api\views.py", line 24, in get
    return JsonResponse({"token": jwt_token.decode("utf-8")})
AttributeError: 'str' object has no attribute 'decode'
[06/Mar/2022 17:43:46] "GET /api/token/alex HTTP/1.1" 500 83352
Internal Server Error: /api/token/alex
Traceback (most recent call last):
  File "C:\Users\User\anaconda3\lib\site-packages\django\core\handlers\exception.py", line 34, in inner
    response = get_response(request)
  File "C:\Users\User\anaconda3\lib\site-packages\django\core\handlers\base.py", line 126, in _get_response
    response = self.process_exception_by_middleware(e, request)
  File "C:\Users\User\anaconda3\lib\site-packages\django\core\handlers\base.py", line 124, in _get_response
    response = wrapped_callback(request, *callback_args, **callback_kwargs)  File "C:\Users\User\anaconda3\lib\site-packages\django\views\generic\base.py", line 68, inn view
    return self.dispatch(request, *args, **kwargs)
  File "C:\Users\User\anaconda3\lib\site-packages\django\views\generic\base.py", line 88, inn dispatch
    return handler(request, *args, **kwargs)
  File "C:\swe\twilio-django-react\api\views.py", line 24, in get
    return JsonResponse({"token": jwt_token.decode("utf-8")})
AttributeError: 'str' object has no attribute 'decode'
[06/Mar/2022 17:50:54] "GET /api/token/alex HTTP/1.1" 500 83352

in ngrok terminal it says 
GET  /api/token/alex           500 Internal Server Error

changed account name on twilio console to 
andrewcbuensalida

now trying 
curl -X GET https://2eec-2600-1010-b046-ad33-c051-6ad9-bbe4-5533.ngrok.io/api/token/andrewcbuensalida
still the same error

had to remove the .decode("utf-8") in api/views.py TokenView because i guess python3 already decodes it. now i get a proper jwt which i can plug into jwt.io to see the username


curl -X GET https://2eec-2600-1010-b046-ad33-c051-6ad9-bbe4-5533.ngrok.io/api/rooms


getting an error
Module not found: Error: Can't resolve 'util' in 'C:\swe\twilio-django-react\audio-chat\node_modules\backoff\lib'
BREAKING CHANGE: webpack < 5 used to include polyfills for node.js core modules by default.
This is no longer the case. Verify if you need this module and configure a polyfill for it.

If you want to include a polyfill, you need to:
        - add a fallback 'resolve.fallback: { "util": require.resolve("util/") }' 
        - install 'util'
If you don't want to include a polyfill, you can use an empty module like this:   
        resolve.fallback: { "util": false }

had to change react-scripts to 4.0.3