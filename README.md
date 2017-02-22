# chatsdk


Ejemplo de enviar mensaje

 sendButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String messageText = messageArea.getText().toString();
                ChatMessage message = new ChatMessage();
                message.setText(messageText);
                message.setTimestamp(System.currentTimeMillis());
                message.setSender(ChatInstance.myUser);
                message.setReceiver(ChatInstance.chatWith);
               chatPresenter.sendMessage(message);
            }
        });
        
Ejemplo de iniciar chat desde listado de usuarios

usersList.setOnItemClickListener(new AdapterView.OnItemClickListener() {
           @Override
            public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
                usersPresenter.initializeChat(userArrayList.get(position));
                startActivity(new Intent(context, ChatActivity.class));
            }
        });

