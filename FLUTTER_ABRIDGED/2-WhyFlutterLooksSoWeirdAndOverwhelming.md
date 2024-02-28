        tl;dr 
        -constructors with optional parameters
        -properties that can have other classes with their own optionnal parameters in


Flutter looks weird because it uses dart and dart has it's little quirks.
The main reason as to why it looks like that is because of the way dart does it's constructors.

REFER TO THE DART_ABRIDGED FOLDER FOR MORE DETAILS

To compare here's how it's usually done in java:

        public class JavaExampe{
            private String someProperty;
            private String anotherProperty;

            public JavaExample(String someProperty, String anotherProperty){
                setSomeProperty(someProperty);
                setAnotherProperty(anotherProperty);
            }

            public void setSomeProperty(String someProperty){
                this.someProperty = someProperty;
            }

            public String getSomeProperty(){
                return this.someProperty;
            }

            public void setAnotherProperty(String anotherProperty){
                this.anotherProperty = anotherProperty;
            }

            public String getAnotherProperty(){
                return this.anotherProperty;
            }
        }

That is what I am used to, that's probably also what you're used to, it's clean it's neat, I like the way it looks.
Dart has the same concepts. However, they do things differently:

        class DartExample{
            var someProperty;
            var anotherProperty;
            DartExample(this.someProperty, this.anotherProperty);
        }

That basically did the same thing as that long ass java class. Quick and efficient (twss roflmao).
In spirit of that quick and efficient mindset, you will often see flutter code like this

        SomeWidget aaaaaaaaaaaaaaaaaaaaaaaaaaa {
            return DartExample(
                someProperty,
                anotherProperty
            )
        }

Also, with dart, you can have optionnal properties,
    meaning that you could just not put those in when initializing the class
    and chose to put some parameters in.
    Thats the thing that was soo fcking confusing to me.
    Hate it, but it's pretty useful ngl

        class DartExample{
            var someProperty;
            var anotherProperty;
            DartExample([this.someProperty, this.anotherProperty]);
        }

Then you could call it like this

        SomeWidget bbbbbbbbbbbbbbbbbbbbbbb {
            return DartExample(
                someProperty: AnotherFuckingClassOrWidget(),
                //notice the other property isn't here, but you could put it in if you wanted to (twss)
            )
        }

        AND YOU CAN PUT ANOTHER FUCKING CLASS/WIDGET INTO IT!!! THIS SHIT CRAY CRAY
