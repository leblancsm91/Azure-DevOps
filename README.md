# LiveProj
the final and live project

I organized the icons in the footer. This had to be done without interrupting functionality of the links. 

    @RenderPage("Chat.cshtml")
   
    <div id="main" class="container body-content">
        @RenderBody()

        <br />
        <hr />

    <footer>
        <div class="float-bottom">
            &copy; @DateTime.Now.Year - Management Portal
        </div>
    </footer>
    <div class="container">
        <div class="row float-right">
        @if (User.Identity.IsAuthenticated)
        {
            //preloader link
            <div class="col">
                @Html.ActionLink("Preloader", "Index", "PreLoader")
            </div>
        }
        @if (User.Identity.IsAuthenticated)
        {
            //printer icon
            <div class="col">
                @using (Html.BeginForm("Export", "Home", FormMethod.Post))
                {
                    <input type="hidden" name="ExportData" />
                    <input type="image" id="btnSubmit" src="~/Content/images/Printer.png" width="80" height="60" value="Export" />
                }
            </div>
        }
        @if (User.Identity.IsAuthenticated)
        {
            //chat icon
            <div class="col">
                <img id="chatIcon" src="~/Content/images/chaticon.jpg" title="Open Messenger" height="60" width="80" onclick="openChat()" />
            </div>
        }
        </div>
        </div>
    </div>
