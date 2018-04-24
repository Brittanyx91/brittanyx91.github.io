---
layout: post
title: BlocChat
thumbnail-path: "img/bloc-chat-room-with-messages-with-send.jpg"
short-description: BlocChat is a chat room where you can talk to your friends.

---

{:.center}
![]({{ http://www.codingwithcats.us }}img/bloc-chat-room-with-messages-with-send.jpg)

## Explanation

In Module Two of my school work with Bloc we were given the task of creating a chat room can send and receive messages and also create new chat rooms with a user sign in.
## Problem

Our first step was to use the NoSQL database Firebase where we stored data objects like rooms and messages for our app. Our next objective was to create an active room that stored our current messages. We also wanted our users to be able to sign in using Google. Our first messages and rooms were created manually in Firebase but now it was time for the user to create them within the app.

## Solution

Initially when working with Firebase I had several problems learning how to structure the objects. After that was solved my rooms came through to my app.
>![Room Structure](https://i.imgur.com/kayoyGX.png "Room Structure")

We needed to set an active room to store our current messages.
>render() {
          const activeRoom = this.props.activeRoom;
          var messageList = this.state.messages.filter(message => message.roomid === activeRoom);
          messageList = messageList.map(message => {
            return <div className="current-message" key={message.key}>{message.username} {message.content} {this.time(message.sentat)} </div>

          })

          return (
                <div className="chatroom-messages">
                    <div>{messageList}
                    </div>
                    <form onSubmit={(e) => this.handleSubmit(e)}>
                        <input type="text" name="newmessage" placeholder="New Message" value={this.state.content}
                        onChange={(e) => this.handleChange(e)} />
                        <button type="submit" onClick={(e) => this.createMessage(e)}>Send</button>
                        </form>
                    </div>
        );
    }
}


Users needed to be able to sign in.
>![Sign In](https://i.imgur.com/aSgkbGo.png "Sign In")


Now users are able to create messages and rooms within the app!
>![Messages](https://i.imgur.com/EPZBpdY.png "Messages")

## Results
After working through each problem given Bloc Chat was proven to be a user friendly application.

## Conclusion
React and Firebase gave me the tools to create a fun project.
