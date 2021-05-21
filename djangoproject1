#I have created this file

from django.http import HttpResponse
from django.shortcuts import render


def index(request):

    return render (request,'index.html')

    #return HttpResponse("hello")

def analyse(request):
    #Get the text
    djtext=(request.GET.get('text','default'))

    #check checkbox values
    removepunc=request.GET.get('removepunc','off')
    uppercase=request.GET.get('uppercase','off')
    newlineremover=request.GET.get('newlineremover','off')
    spaceremover=request.GET.get('spaceremover','off')

    #print(removepunc)

    #print(djtext)

    #check with checkbox is on
    #to remove punctuation
    if removepunc =='on':
        punctuation ='''!()-[]{}:;'"\,<>./?@#$%^&*_~'''
        analysed=""
        for i in djtext:
            if i not in punctuation:
                analysed=analysed+i
        parame={'purpose':'removepunctuation','analysed_text':analysed}
        return render(request,'analyse.html',parame)

   #for capitalise the text
    elif(uppercase == 'on'):
        analysed =""
        for i in djtext:
            analysed=analysed+i.upper()
        parame = {'purpose': 'change to uppercase', 'analysed_text': analysed}
        return render(request, 'analyse.html', parame)

    #to removenewline
    elif(newlineremover=="on"):
        analysed=""
        for i in djtext:
            analysed=analysed+i
        parame = {'purpose': 'remove new line', 'analysed_text': analysed}
        return render(request, 'analyse.html', parame)
    #for space remover
    elif(spaceremover=="on"):
        analysed=""
        for i in (djtext):
            analysed=djtext.split(' ')
            analysed=' '.join(analysed)


        parame = {'purpose': 'spaceremover', 'analysed_text': analysed}
        return render(request, 'analyse.html', parame)
    else:
        #djtext = (request.GET.get('text', 'default'))
        parame = {'purpose': 'removepunctuation', 'analysed_text': djtext}
        return render(request,'analyse.html',parame)
        #return HttpResponse('error')

#def capitalise(request):
 #   return HttpResponse('capitalised')

#def newlineremover(request):
 #   return HttpResponse('newlineremover')

#def spaceremover(request):
 #   return HttpResponse('spaceremover')

#def charcount(request):
 #   return HttpResponse('charcount')

#def analyse(request):
#    return HttpResponse("Harshal")

