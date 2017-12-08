# utl_proc_odstext_and_ods_tagsets_text
I did not know that: proc odstext and ods tagsets text.  Is there a way to page break between 2 ods text lines with out using a space line?
    Proc odstext and ods tagsets text

    pdf output
    https://goo.gl/k4gQQY
    https://github.com/rogerjdeangelis/utl_proc_odstext_and_ods_tagsets_text/blob/master/utl_proc_odstext_and_ods_tagsets_text.pdf

    rtf output
    https://goo.gl/WZYBwd
    https://github.com/rogerjdeangelis/utl_proc_odstext_and_ods_tagsets_text/blob/master/utl_proc_odstext_and_ods_tagsets_text.rtf

    Original topic: How do you page break between 2 ODS Test lines
    Is there a way to page break between 2 ods text lines with out using a space line?

    see
    https://goo.gl/srDJC8
    https://communities.sas.com/t5/SAS-Procedures/How-do-you-page-break-between-2-ODS-Test-lines/m-p/419613

    Reeza profile
    https://communities.sas.com/t5/user/viewprofilepage/user-id/13879

    ballardw profile
    https://communities.sas.com/t5/user/viewprofilepage/user-id/13884

    *          _  __             _     _            _
     _ __   __| |/ _|   ___   __| |___| |_ _____  _| |_
    | '_ \ / _` | |_   / _ \ / _` / __| __/ _ \ \/ / __|
    | |_) | (_| |  _| | (_) | (_| \__ \ ||  __/>  <| |_
    | .__/ \__,_|_|    \___/ \__,_|___/\__\___/_/\_\\__|
    |_|
    ;


    ods pdf file='d:/pdf/utl_proc_odstext_and_ods_tagsets_text.pdf' style=meadow startpage=no ;;

    proc odstext pagebreak=on;
       p 'You can use the ODSTEXT procedure to add paragraphs
          and lists to your output.';
       p 'You can also format your text.' / style=[color=red fontsize=25pt];
       p 'This slide shows output created by PROC GMAP.'
                                         / style=[color=purple fontsize=30pt];
    run;

    proc odstext;
       p 'You can use the ODSTEXT2 procedure to add paragraphs
          and lists to your output.';
    run;

    ods pdf close;

    *     _    __   _                       _         _            _
     _ __| |_ / _| | |_ __ _  __ _ ___  ___| |_ ___  | |_ _____  _| |_
    | '__| __| |_  | __/ _` |/ _` / __|/ _ \ __/ __| | __/ _ \ \/ / __|
    | |  | |_|  _| | || (_| | (_| \__ \  __/ |_\__ \ | ||  __/>  <| |_
    |_|   \__|_|    \__\__,_|\__, |___/\___|\__|___/  \__\___/_/\_\\__|
                             |___/
    ;

    ods escapechar='^' ;

    ods tagsets.rtf file='d:/rtf/utl_proc_odstext_and_ods_tagsets_text.rtf'
     options(Tables_OFF='USERTEXT');

    ods tagsets.rtf text='example of forced page break in rtf ^{raw\page} in the middle of text';
    proc print data=sashelp.class (obs=5) ;
    run;
    ods tagsets.rtf text='example of forced page break in rtf between ods text statments';
    ods tagsets.rtf text='^{raw \page} ';
    ods tagsets.rtf text='following text statement';

    ods tagsets.rtf close;

