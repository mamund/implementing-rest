# Introduction #
This article is a stub for the Mind Touch Dream framework

# Mind Touch Dream #
_From the project home page:_

Mind Touch Dream is a Web-Oriented Architecture Framework (WOAF) for developing lightweight, highly decoupled web-services.  The framework includes of a REST microserver and classes for web communication, XML processing, and writing highly asynchronous code.

_From a sample [tutorial page](http://developer.mindtouch.com/Dream/Tutorials/Creating_a_Magic_8-Ball_service):_
```
namespace MindTouch.Dream.Samples {
    using Yield = System.Collections.Generic.IEnumerator<IYield>;

    [DreamService("Dream Tutorial 8-Ball", "Copyright (c) 2006, 2007 MindTouch, Inc.",
        Info = "http://doc.opengarden.org/Dream/Samples/8-Ball",
        SID = new string[] { "http://services.mindtouch.com/dream/tutorial/2007/03/8ball" }
    )]
    public class EightBallService : DreamService {
        private static System.Random _random = new System.Random();
        private static string[] _answers = new string[] {
            "Reply hazy, try again", "Without a doubt", "My sources say no", "As I see it, yes" 
        };

        [DreamFeature("GET:", "Returns a random 8-ball message")]
        public Yield GetAnswer(DreamContext context, DreamMessage request, Result<DreamMessage> response) {
            response.Return(DreamMessage.Ok(MimeType.TEXT, "The 8-ball says: " + _answers[_random.Next(_answers.Length)]));
            yield break;
        }
    }
}
```